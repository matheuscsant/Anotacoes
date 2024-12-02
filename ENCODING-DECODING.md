# Manual de encoding/decoding

## Sumário

1. [Base64](#base64)
2. [Base32](#base32)
3. [Escopo geral](#escopo-geral-de-diferenças)

## Base64

1. Abrangência de caracteres: `A-Z`, `a-z`, `0-9`, `+` e `/`
2. Case sensitive
3. Comprimento: Múltiplos de 4 (Típico, não é regra)
4. Mais compacto: 6 bits/caracteres (Mesma quantidade de dados, menos caracteres que [Base32](#base32))
5. **Utilidade: Certificados, Arquivos, dados binários em geral...**
    > Para codificações base64, espaços em branco (" "), no meio da string codificada,
    não é considerado válido, mesma coisa serve para caso a string codificada contenha caracteres
    com encoding de URL ("%2B" = "+", "%3D" = "=", "%2F" = "/"), deve ser convertido antes de tentar
    fazer o encoding/decoding. Naturalmente encoding em Base64, termina com "=", mas não é regra.
6. Exemplo:
   ```
   TWFuIGlzIGRpc3Rpbmd1aXNoZWQsIG5vdCBvbmx5IGJ5IGhpcyByZWFzb24sIGJ1dCAuLi4=
   "Man is distinguished, not only by his reason, but ..."
   ```

## Base32

1. Abrangência de caracteres: `A-Z` e `2-7`
2. Somente maiúscilas
3. Comprimento: Múltiplos de 8 (Típico, não é regra)
4. Menos compacto: 5 bits/caracteres (Mesma quantidade de dados, mais caracteres que [Base64](#base64))
5. **Utilidade: TOPT/HOTP (2FA), QRCodes...**
6. Exemplo:
    ```
    JVQW4IDJOMQGI2LTORUW4Z3VNFZWQZLEFQQG433UEBXW43DZEBRHSIDINFZSA4TFMFZW63RMEBRHK5BAFYXC4===
    "Man is distinguished, not only by his reason, but ..."
    ```

## Escopo geral de diferenças

| Característica          | Base32                          | Base64                          |
|-------------------------|----------------------------------|----------------------------------|
| **Conjunto de caracteres** | `A-Z`, `2-7`                    | `A-Z`, `a-z`, `0-9`, `+`, `/`.  |
| **Sensível a maiúsculas**   | Não                             | Sim.                            |
| **Comprimento típico**      | Múltiplos de 8                  | Múltiplos de 4                  |
| **Eficiência**              | Menos compacta (5 bits/caractere) | Mais compacta (6 bits/caractere) |
| **Uso comum**               | Códigos TOTP/HOTP (2FA), QR Codes | Certificados, dados binários complexos. |

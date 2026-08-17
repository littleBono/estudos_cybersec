# Sistemas Numéricos & Encoding

> Fundamentos de binário, decimal, hexadecimal, octal e encoding de caracteres (ASCII/Unicode/UTF-8).

## Unidades

| Termo | Bits |
|---|---|
| Bit | 1 |
| Nibble | 4 |
| Byte | 8 |

`2ⁿ − 1` = valor máximo representável com `n` bits.
- 4 bits → `2⁴ − 1 = 15` (0-F em hex)
- 8 bits → `2⁸ − 1 = 255` (1 byte)
- 32 bits → `2³² − 1 = 4.294.967.295` (limite IPv4)

## Binário → Decimal

Some as potências de 2 onde o bit é `1`.

## Hex → Binário (1 dígito = 1 nibble)

Não converta hex→decimal direto — passe por binário.

2 dígitos hex = 1 byte exato (por isso cores, endereços de memória etc. sempre vêm em pares).

## Octal → Permissões Linux (`chmod`)

3 bits por dígito, sempre na ordem **r(4) w(2) x(1)**, para **Dono / Grupo / Outros**:

| Octal comum | Uso |
|---|---|
| `644` | arquivos comuns (dono edita, resto só lê) |
| `755` | pastas/executáveis |
| `600` | arquivos sensíveis (ex: chave SSH) |
| `777` | tudo liberado — evitar (viola menor privilégio) |

## ASCII

Blocos de início: `0-9`=48, `A-Z`=65, `a-z`=97. Ex: `'C'` = 65+2 = 67.

## Unicode / UTF-8/16/32

- **UTF-8**: tamanho variável (1-4 bytes), compatível com ASCII
- **UTF-16**: quase-fixo (2 bytes, exceto surrogate pairs)
- **UTF-32**: tamanho fixo (4 bytes) — simples, mas ocupa mais espaço

## Por que converter?

- **Binário** = linguagem real do hardware
- **Decimal** = legível pra humano
- **Hex/Octal** = representação compacta do binário, mais fácil de ler/escrever

**Onde aparece em cibersegurança**: assinaturas de arquivo em hexdump (ex: PDF = `25 50 44 46`), máscaras de sub-rede, endereços de memória em exploração de binários, permissões de arquivo Linux.

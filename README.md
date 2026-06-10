# dim-geografia-brasil
Tabela dimensional com os 5.571 municípios brasileiros — hierarquia geográfica vigente (Regiões Imediatas e Intermediárias IBGE 2025), DDD e capital. Pronta para uso em Power BI, PROCV/XLOOKUP e CRM.
# dim-geografia-brasil

Tabela dimensional geográfica com todos os 5.571 municípios brasileiros,
pronta para uso em Power BI, PROCV/XLOOKUP e CRM.

## Colunas

| Coluna | Descrição |
|---|---|
| `codigo_ibge` | Código IBGE do município (7 dígitos) — chave principal |
| `cidade` | Nome oficial do município |
| `cidade_sem_acento` | Nome em maiúsculas sem acento — para JOIN sem erro de acentuação |
| `uf` | Sigla do estado (ex: SP, PR) |
| `estado` | Nome do estado |
| `capital` | TRUE se for capital estadual |
| `ddd` | Código de área telefônico |
| `regiao_imediata` | Região Geográfica Imediata (divisão vigente IBGE desde 2017) |
| `codigo_regiao_imediata` | Código da Região Imediata |
| `regiao_intermediaria` | Região Geográfica Intermediária |
| `codigo_regiao_intermediaria` | Código da Região Intermediária |
| `regiao` | Macrorregião (Norte, Nordeste, etc.) |
| `pais` | Brasil |

## Fontes

- **Hierarquia geográfica:** API IBGE Localidades — divisão vigente 2017
- **DDD e capital:** [kelvins/municipios-brasileiros](https://github.com/kelvins/municipios-brasileiros)
- **Validado contra:** DTB IBGE 2025

## Como usar no Power BI

Importe o arquivo `.xlsx` como tabela e relacione com sua tabela fato
pelo campo `codigo_ibge`.

Para PROCV/XLOOKUP, use `cidade_sem_acento + uf` como chave
para evitar quebra por diferença de acentuação entre sistemas.

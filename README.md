# PROJETO-LAKEHOUSE-COM-DATABRICKS-E-ARQUITETURA-MEDALHAO

## Integrantes

- William Manoel Bitencourt Mesquita

## Estrutura do Repositório

```text
.
├── data/
│   └── landing
│       ├──apolice.csv
│		├──carro.csv
│		├──cliente.csv
│		├──endereco.csv
│		├──estado.csv
│		├──marca.csv
│		├──modelo.csv
│		├──municipio.csv
│		├──regiao.csv
│		├──sinistro.csv
│		└──telefone.csv
│
├── docs/
│   └── notebook_iceberg.ipynb
│
notebooks/
├── setup/
│   └── 001_preparando_ambiente.dbc
├── bronze/
│   └── 002_bronze.dbc
├── silver/
│   └── 003_silver.dbc
├── gold/
│   └── 004_gold.dbc
├── cleanup/
│   └── 005_destruindo_ambiente.dbc
│
└── README.md
```
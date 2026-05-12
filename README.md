# PROJETO-LAKEHOUSE-COM-DATABRICKS-E-ARQUITETURA-MEDALHAO

## Integrantes

- William Manoel Bitencourt Mesquita

## Estrutura do Repositório

```text
.
├── data/
│   └── landing
│       ├── agent_policies.csv
│		    ├── agents.csv
│		    ├── claims.csv
│		    ├── customers.csv
│		    ├── insurance_types.csv
│		    ├── payments.csv
│		    └── policies.csv
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
├── LICENSE
└── README.md
```

## Licença

Este projeto é distribuído sob a licença **MIT**.

É permitido:
- Usar, copiar, modificar e distribuir este projeto
- Utilizar o código para fins acadêmicos, pessoais ou profissionais

Não é permitido:
- Responsabilizar o autor por qualquer dano, perda de dados ou problema decorrente do uso deste projeto

Este repositório foi criado **exclusivamente para fins educacionais**.  
O autor **não se responsabiliza** por qualquer uso indevido ou consequências decorrentes da utilização do código.

Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

## Links e Referências

- Repositório com .csvs utilizados:
  https://github.com/AmonAmarth2003/spark-delta-minio-sqlserver

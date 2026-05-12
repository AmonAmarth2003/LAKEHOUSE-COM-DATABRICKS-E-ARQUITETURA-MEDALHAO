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
│   └── Empty
│
├── notebooks/
│   ├── setup/
│   │   └── 001_preparando_ambiente.dbc
│   ├── bronze/
│   │   └── 002_bronze.dbc
│   ├── silver/
│   │   └── 003_silver.dbc
│   ├── gold/
│   │   └── 004_gold.dbc
│   └── cleanup/
│       └── 005_destruindo_ambiente.dbc
│
├── LICENSE
└── README.md
```

## Visão Geral do Projeto

Este projeto implementa um pipeline de dados no modelo **Lakehouse** utilizando o **Databricks Free Edition** e a arquitetura **Medalhão (Medallion Architecture)**: Landing → Bronze → Silver → Gold.

O objetivo é construir um pipeline completo de engenharia de dados que ingere dados brutos, processa em múltiplas camadas e entrega dados prontos para análise.

---

## Arquitetura
O pipeline é orquestrado utilizando **Databricks Jobs**, garantindo execução sequencial da arquitetura medalhão:
Landing → Bronze → Silver → Gold

### Landing
- Armazena arquivos CSV brutos
- Sem qualquer transformação
- Dados são carregados em Volumes no Databricks

### Bronze
- Converte os dados brutos em tabelas Delta
- Adiciona metadados de ingestão:
  - `date_hour_bronze`
  - `file_name`
- Representa dados crus com rastreabilidade

### Silver
- Aplica limpeza e padronização dos dados
- Remove metadados da camada Bronze
- Adiciona novos metadados:
  - `date_hour_silver`
  - `table_name`
- Produz dados confiáveis e estruturados

### Gold
- Implementa modelo dimensional (Kimball)
- Cria:
  - Tabelas de dimensão (`dim_*`)
  - Tabelas fato (`fact_*`)
- Otimizada para análise e BI

---

## Dataset

O projeto utiliza um conjunto de dados do domínio de seguros, com as seguintes tabelas:

- `agent_policies`
- `agents`
- `claims`
- `customers`
- `insurance_types`
- `payments`
- `policies`

---

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

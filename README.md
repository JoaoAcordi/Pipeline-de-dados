
# 🧠 Projeto: Pipeline de Dados com Databricks e Delta Lake

## 📘 Descrição
Este projeto implementa um pipeline completo baseado na **Arquitetura Medalhão (Medallion Architecture)** utilizando **Delta Lake** dentro do **Databricks**.

O pipeline possui três camadas principais:
- **Landing → Bronze:** ingestão dos dados brutos
- **Bronze → Silver:** limpeza e transformação
- **Silver → Gold:** agregação e geração de insights

## 🚀 Estrutura
```
pipeline_databricks/
│
├── data/
│   ├── movies_top100.csv
│   ├── movies_ratings.csv
│   ├── movies_revenue.csv
│   ├── movies_casts.csv
│   └── movies_meta.csv
│
├── notebooks/
│   ├── 1_landing_to_bronze.py
│   ├── 2_bronze_to_silver.py
│   ├── 3_silver_to_gold.py
│
└── docs/
    ├── index.md
    ├── arquitetura.md
    ├── pipeline.md
    ├── databricks_job.md
    └── contato.md
```

## 🧩 Como Rodar
1. Suba o projeto no **Databricks Repos** ou GitHub.
2. Crie as pastas no **DBFS** (`/mnt/datalake/landing`, `/mnt/datalake/bronze`, etc).
3. Execute os notebooks na sequência:  
   `1_landing_to_bronze` → `2_bronze_to_silver` → `3_silver_to_gold`
4. Configure um **Job** e uma **Pipeline** no Databricks para orquestração.

## 📘 Documentação com MkDocs
Para rodar o site da documentação localmente:
```bash
pip install mkdocs
mkdocs serve
```

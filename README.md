# 🎬 Pipeline de Dados com Databricks e Delta Lake — Arquitetura Medalhão

## 🧩 Visão Geral

Este projeto implementa um **Pipeline de Dados** completo utilizando o **Databricks**, **Delta Lake** e a **Arquitetura Medalhão (Medallion Architecture)**, com o objetivo de processar e analisar dados de filmes.

O processo percorre três camadas principais — **Landing**, **Bronze**, **Silver** e **Gold** — cada uma com um propósito distinto na transformação e qualidade dos dados.

---

## 🗂️ Estrutura do Projeto

```
📁 Pipeline-de-dados/
│
├── data/
│   ├── landing/            # Dados brutos (arquivos CSV)
│   ├── bronze/             # Dados limpos e padronizados
│   ├── silver/             # Dados integrados
│   └── gold/               # Dados prontos para análise
│
├── notebooks/
│   ├── 1_landing_to_bronze.py
│   ├── 2_bronze_to_silver.py
│   └── 3_silver_to_gold.py
│
├── docs/                   # Documentação do MKDocs
│   ├── index.md
│   ├── arquitetura.md
│   ├── pipeline.md
│   ├── databricks_job.md
│   └── contato.md
│
├── mkdocs.yml              # Configuração do site MKDocs
└── README.md
```

---

## ⚙️ Tecnologias Utilizadas

* **Databricks**
* **Apache Spark (PySpark)**
* **Delta Lake**
* **MKDocs**
* **GitHub (integração de versionamento)**

---

## 🔁 Fluxo da Arquitetura Medalhão

| Camada      | Descrição                                                        |
| ----------- | ---------------------------------------------------------------- |
| **Landing** | Área onde os arquivos CSV originais são armazenados.             |
| **Bronze**  | Dados brutos são lidos, padronizados e salvos em formato Delta.  |
| **Silver**  | Dados integrados de várias tabelas, com tratamento e junções.    |
| **Gold**    | Dados agregados e refinados, prontos para dashboards e análises. |

---

## 🧠 Notebooks e Funções

### 1️⃣ `1_landing_to_bronze.py`

* Lê arquivos CSV da pasta *landing*.
* Padroniza nomes das colunas.
* Grava as tabelas em formato Delta na camada Bronze.

### 2️⃣ `2_bronze_to_silver.py`

* Lê tabelas Delta da camada Bronze.
* Realiza joins e normalização de tipos.
* Grava os dados integrados na camada Silver.

### 3️⃣ `3_silver_to_gold.py`

* Gera métricas finais (ex: top 10 filmes por ano).
* Escreve os resultados na camada Gold.

---

## 🧱 Execução da Pipeline no Databricks

1. **Envie os arquivos CSV** para o diretório `/Volumes/movies_catalog/landing/`.
2. **Execute os notebooks** na ordem:

   * `1_landing_to_bronze`
   * `2_bronze_to_silver`
   * `3_silver_to_gold`
3. **Crie um Job e Pipeline** no Databricks:

   * Adicione os três notebooks.
   * Configure a execução orquestrada.
   * Execute e valide os dados nas camadas.

---

## 🌐 Documentação com MKDocs

### 1️⃣ Instalar o MKDocs

```bash
pip install mkdocs mkdocs-material
```

### 2️⃣ Rodar localmente

```bash
mkdocs serve
```

O site ficará disponível em:
👉 [http://127.0.0.1:8000](http://127.0.0.1:8000)

### 3️⃣ Gerar a documentação estática

```bash
mkdocs build
```

Os arquivos serão gerados na pasta `site/`.

---

## 📬 Contato

**Autor:** João
**Instituição:** SATC
**Disciplina:** Engenharia de Dados
**Professor:** —
**Ano:** 2025

---

🎯 **Objetivo:** demonstrar um pipeline de dados funcional, documentado e orquestrado via Databricks, com boas práticas de organização e versionamento.

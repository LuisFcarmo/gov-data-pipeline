# 🚀 govbr-data-pipeline

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📖 Sobre o Projeto

Este projeto implementa um pipeline de dados end-to-end para coletar, processar, armazenar e analisar dados de licitações e contratos públicos do Governo Federal do Brasil. O objetivo é criar uma fonte de dados consolidada e confiável (Data Warehouse) para extrair insights analíticos sobre os gastos públicos.

Este repositório serve como um projeto de portfólio, demonstrando habilidades em Engenharia de Dados, Arquitetura de Nuvem na AWS e automação de processos.

---

## 📊 Status do Projeto

- [x] **Fase 1: Ingestão (Camada Bronze)** - Coleta de dados brutos e armazenamento no Data Lake.
- [ ] **Fase 2: Transformação (Camada Prata)** - Limpeza e padronização dos dados com AWS Glue.
- [ ] **Fase 3: Modelagem e Carga (Camada Ouro)** - Carga dos dados no Data Warehouse (Redshift).
- [ ] **Fase 4: Análise e Visualização** - Criação de consultas analíticas.
- [ ] **Fase 5: Automação e Deploy** - Orquestração com Step Functions e IaC com Terraform.

---

## 🏛️ Diagrama da Arquitetura

*Obs: O diagrama final será inserido aqui. Ferramenta sugerida: [draw.io](https://app.diagrams.net/)*

O fluxo de dados segue a arquitetura abaixo:

![Diagrama da Arquitetura](https://via.placeholder.com/800x400.png?text=WIP%3A+Diagrama+da+Arquitetura+do+Pipeline)

* **Fontes de Dados:** Portais do Governo Federal (ex: Portal da Transparência).
* **Ingestão:** Um scraper em Python coleta os dados e os salva em formato JSON no **AWS S3** (Data Lake - Camada Bronze).
* **ETL:** O **AWS Glue** processa os dados brutos, limpando-os e convertendo para Parquet na Camada Prata.
* **Data Warehouse:** O **AWS Redshift** armazena os dados modelados (Star Schema) na Camada Ouro para consultas de alta performance.
* **Análise:** Ferramentas de BI e clientes SQL consomem os dados do Redshift.
* **Orquestração:** O **AWS Step Functions** gerencia o fluxo de execução do pipeline.
* **Infraestrutura:** O **Terraform** provisiona e gerencia todos os recursos na nuvem.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:**
  ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
- **Cloud (AWS):**
  ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
  ![S3](https://img.shields.io/badge/S3-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)
  ![Glue](https://img.shields.io/badge/Glue-4D5C7F?style=for-the-badge&logo=aws-glue&logoColor=white)
  ![Redshift](https://img.shields.io/badge/Redshift-8C4785?style=for-the-badge&logo=amazon-redshift&logoColor=white)
  ![Step Functions](https://img.shields.io/badge/Step%20Functions-D52441?style=for-the-badge&logo=aws-step-functions&logoColor=white)
- **Infraestrutura como Código:**
  ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
- **Bibliotecas Python:**
  - Scrapy / Requests
  - Boto3
  - Pandas (para exploração)

---

## ⚙️ Configuração e Instalação

Siga os passos abaixo para configurar o ambiente de desenvolvimento local.

**Pré-requisitos:**
* Conta na AWS com credenciais configuradas localmente.
* Python 3.9+
* Terraform (para as fases futuras)

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/govbr-data-pipeline.git](https://github.com/seu-usuario/govbr-data-pipeline.git)
    cd govbr-data-pipeline
    ```

2.  **Crie e ative um ambiente virtual:**
    ```bash
    python -m venv .venv
    # Windows
    .\.venv\Scripts\activate
    # macOS / Linux
    source .venv/bin/activate
    ```

3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Configure suas credenciais:**
    * **Método 1 (Recomendado):** Use o AWS CLI.
        ```bash
        aws configure
        ```
    * **Método 2:** Crie um arquivo `.env` na raiz do projeto (ele será ignorado pelo Git) e adicione suas chaves:
        ```
        # .env
        AWS_ACCESS_KEY_ID=SUA_CHAVE_DE_ACESSO
        AWS_SECRET_ACCESS_KEY=SUA_CHAVE_SECRETA
        AWS_REGION=sua-regiao
        ```

---

## 🚀 Como Executar

### Fase 1: Ingestão de Dados

Para executar o script de ingestão e salvar os dados no S3:

1.  Navegue até a pasta de ingestão:
    ```bash
    cd src/ingestion
    ```

2.  Execute o script principal do scraper:
    *(Exemplo - ajuste conforme o nome do seu script)*
    ```bash
    python scraper_principal.py --bucket_name "seu-bucket-de-dados-bronze"
    ```

---

## 📁 Estrutura do Projeto
/govbr-data-pipeline/
|
├── .gitignore             # Ignora arquivos desnecessários
├── README.md              # Documentação do projeto
├── requirements.txt       # Dependências Python
|
├── infra/                 # Código Terraform (IaC)
|
├── notebooks/             # Notebooks para exploração e testes
|
└── src/                   # Código-fonte da aplicação
|
├── ingestion/         # Scripts de coleta de dados (Scrapers)
|
├── transformation/    # Scripts ETL para o AWS Glue
|
└── dwh/               # Scripts SQL (Schema DDL, DML)

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👨‍💻 Autor

Feito por **[Luis Cesar Ferreira do Carmo]**

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/luis-cesar-ferreira-do-carmo/)
[![github](https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/LuisFcarmohttps://github.com/LuisFcarmo)
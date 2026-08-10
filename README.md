<details>
<summary>🇬🇧 English Version (click to expand)</summary>

# 🇬🇧 E-commerce Analytics Dashboard Project

This repository contains the solution developed for the project of the Analytics Deepening module, focusing on data processing, SQL database integration, and exploratory analysis for an e-commerce platform.

---

## 1. Project Overview

### Problem Statement and Relevance
In modern retail and e-commerce operations, consolidating transaction logs with customer demographics is vital for identifying sales trends, regional distribution, and consumer behavior. This project bridges raw transactional logs and customer profiles using an automated pipeline to facilitate interactive dashboard creation.

### Data Source and Structure
* **Provided Files:** 
  * `TB_TRANSACOES_PROJETO_ECOMM.csv`: Contains customer transaction records, including transaction ID/client ID, product category, price, and card type.
  * `TB_CLIENTES_PROJETO_ECOMM.csv`: Contains customer personal data, such as client ID, first name, gender, job title, and state location.
* **Relational Key:** Both tables are linked via the `id_client` identifier.

---

## 2. Modeling & Implementation

### Data Treatment and SQL Integration
1. **Database Setup:** Integration of CSV files into an in-memory SQLite database using Python (`sqlite3` and `pandas`).
2. **Relational Join:** Execution of an `INNER JOIN` strategy based on `id_client`. 
   * *Justification:* The `INNER JOIN` ensures that the final dataset focuses strictly on active clients who completed transactions, avoiding null fields or data integrity issues associated with unmatched records.
3. **Data Export:** The consolidated dataset is successfully exported as a clean CSV file (`dados_ecommerce_final.csv`) ready for BI tools like Power BI or Looker Studio.

---

## 3. Conclusions and Project Tips

### Key Guidelines for Visualization
1. **Metric Aggregation:** Because individual clients may perform multiple transactions, unique identifiers (`DISTINCT`) must be handled properly when computing client-level metrics to prevent data repetition.
2. **Exploratory Analysis:** Reviewing dimensions and table schemas beforehand streamlines the creation of interactive layouts in BI applications.

</details>

---

# 🇧🇷 Projeto de Dashboard de E-commerce para Analytics

Este repositório contém a solução desenvolvida para o projeto do módulo de aprofundamento em analytics, focando no tratamento de dados, cruzamento via SQL e consolidação de bases para análise de e-commerce.

---

## 1. Visão Geral do Projeto

### Problemática e Relevância
No ecossistema de lojas virtuais, unificar os registros de transações com os dados demográficos dos clientes é essencial para extrair insights sobre vendas, comportamento de compra e distribuição geográfica. Este projeto automatiza a unificação de fontes distintas para preparar os dados para ferramentas de visualização (Power BI ou Looker Studio).

### Estrutura dos Dados
* **Bases Disponibilizadas:**
  * `TB_TRANSACOES_PROJETO_ECOMM.csv`: Registros de transações contendo o ID do cliente, categoria do produto, preço e tipo de cartão.
  * `TB_CLIENTES_PROJETO_ECOMM.csv`: Dados cadastrais dos clientes contendo nome, gênero, cargo, estado (`state_name`) e ID do cliente.
* **Chave de Ligação:** A coluna `id_client` atua como chave relacional entre as tabelas.

---

## 2. Metodologia e Implementação

### Processamento via SQL e Python
1. **Configuração do Ambiente:** Utilização de Python com as bibliotecas `pandas` e `sqlite3` para carregar os arquivos CSV e estruturá-los em um banco de dados SQLite local (`projeto.db`).
2. **Cruzamento de Dados (`JOIN`):** Aplicação de um `INNER JOIN` unificando as tabelas por `id_client`.
   * *Justificativa:* O `INNER JOIN` foi escolhido por focar estritamente nos clientes que realizaram transações, assegurando a integridade analítica e evitando valores nulos que surgiriam com o uso de um `LEFT JOIN`.
3. **Exportação:** Geração da base consolidada exportada no arquivo `dados_ecommerce_final.csv`.

---

## 3. Conclusões e Recomendações

### Boas Práticas para o Dashboard
1. **Métricas Distintas:** Como um mesmo cliente pode efetuar múltiplas compras, recomenda-se o uso de contagens distintas (`DISTINCT`) ao criar métricas centradas no perfil do cliente para evitar distorções de volume.
2. **Roteiro Prévio:** Planejar as dimensões e o layout das visualizações antecipadamente agiliza a construção dos relatórios interativos.

# 📈 Análise de Evasão de Clientes (Churn): Telecom X

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/WBruni/analise-churn-telecom-x/blob/main/TelecomX_BR.ipynb)
[![Link do NBViewer](https://img.shields.io/badge/render-nbviewer-orange?style=flat&logo=jupyter)](https://nbviewer.org/github/WBruni/analise-churn-telecom-x/blob/main/TelecomX_BR.ipynb)

## 📋 Sobre o Projeto
Este projeto apresenta uma análise profunda dos fatores que influenciam o **Churn** (cancelamento de serviços) na Telecom X. Através de uma abordagem de Análise Exploratória de Dados (EDA), identificamos padrões demográficos, contratuais e financeiros que permitem à empresa antecipar perdas e otimizar o Lifetime Value (LTV) da base de clientes.

---

## 🔍 **Análise da Estrutura dos Dados**
Os dados são organizados em um formato hierárquico, contendo as seguintes informações:

1. **Identificação do Cliente**  
   - `'customerID'`: Identificador único do cliente.  
   - `'Churn'`: Indica se o cliente cancelou o serviço (`Yes` ou `No`).  

2. **Informações do Cliente** (`'customer'`)  
   - `'gender'`: Gênero do cliente (`Male` ou `Female`).  
   - `'SeniorCitizen'`: Indica se o cliente é idoso (0 = Não, 1 = Sim).  
   - `'Partner'`: Se o cliente tem um parceiro(a).  
   - `'Dependents'`: Se o cliente tem dependentes.  
   - `'tenure'`: Tempo de permanência como cliente (em meses).  

3. **Serviços de Telefonia** (`'phone'`)  
   - `'PhoneService'`: Indica se o cliente possui serviço de telefone (`Yes` ou `No`).  
   - `'MultipleLines'`: Se possui múltiplas linhas telefônicas.  

4. **Serviços de Internet** (`'internet'`)  
   - Tipo de serviço de internet contratado (`DSL`, `Fiber optic`, `No`).  
   - Serviços adicionais (`OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`).  

5. **Informações da Conta** (`'account'`)  
   - `'Contract'`: Tipo de contrato (`Month-to-month`, `One year`, `Two year`).  
   - `'PaperlessBilling'`: Se o cliente recebe faturas eletrônicas.  
   - `'PaymentMethod'`: Método de pagamento (`Bank transfer`, `Credit card`, `Electronic check`, `Mailed check`).  
   - `'Charges'`:  
     - `'Monthly'`: Valor mensal cobrado.  
     - `'Total'`: Valor total pago pelo cliente.  

---

## 📊 Galeria de Análise (Data Insights)

### 1. Visão Geral e Estrutura de Dados
A taxa de `Churn` de **26,6%** serve como nossa métrica principal. A matriz de calor revela as relações numéricas entre tempo de casa e cobranças.

| Distribuição de Churn (Baseline) | Matriz de Correlação Geral |
| :---: | :---: |
| ![Churn](images/Distribuicao_Churn.png) | ![Heatmap](images/Matriz_corr.png) |

### 2. Infraestrutura e Serviços Agregados
Identificamos que a Fibra Óptica é um ponto de alta volatilidade, enquanto serviços de segurança retêm o cliente.

| Impacto da Tecnologia de Internet | Valor dos Serviços de Segurança/Suporte |
| :---: | :---: |
| ![Infra](images/Servicos_Infra.png) | ![Agregados](images/Servicos_Agregados.png) |

### 3. Perfil do Cliente e Comportamento Digital
Clientes sem dependentes e usuários de fatura digital/cheque eletrônico apresentam maior propensão à troca de operadora.

| Análise Demográfica (Dependentes/Parceiros) | Impacto da Fatura Digital e Pagamento |
| :---: | :---: |
| ![Demografia](images/Analise_Demografica.png) | ![Financeiro](images/Analise_Contratual_Fianceira.png) |

### 4. Ciclo de Vida e Custos Mensais
O risco de saída é crítico no início da jornada. O valor da mensalidade (Monthly Charges) é um gatilho direto para o cancelamento.

| Distribuição de Mensalidades (Monthly Charges) | Correlação Tenure vs. Churn |
| :---: | :---: |
| ![Mensalidade](images/Analise_Tenure_Custos_1.png) | ![Tenure](images/Corr_Tenure_Custo.png) |

---
## 🔍 Principais Insights

* **Contratos e Fidelidade**: Contratos **Mensais** possuem a maior correlação positiva com o Churn, enquanto o modelo **Bienal** garante a maior lealdade.
* **Serviços "Âncora"**: A presença de **Suporte Técnico** e **Segurança Online** atua como uma barreira de saída; clientes sem esses serviços evadem com muito mais frequência.
* **O Risco da Fibra**: Clientes de **Fibra Óptica** apresentam maior propensão ao churn, sugerindo alta sensibilidade a preço ou forte concorrência neste segmento.
* **Zona de Risco Inicial**: O churn é extremamente concentrado nos **primeiros meses** (baixo Tenure). Clientes que ultrapassam o primeiro ano tendem a se estabilizar.
* **Meios de Pagamento**: O uso de **Cheque Eletrônico** é um forte preditor de evasão, enquanto pagamentos automáticos favorecem a retenção.

---

## 💡 Recomendações Estratégicas

1.  **Migração Contratual**: Oferecer benefícios para converter clientes de contratos mensais para planos Anuais ou Bienais.
2.  **Bundling de Utilidades**: Incluir serviços de segurança e suporte como padrão em planos de alto valor para aumentar a fidelidade.
3.  **Onboarding Intensivo**: Implementar ações de Customer Success focadas nos primeiros 6 meses de contrato para mitigar o churn precoce.
4.  **Automação Financeira**: Incentivar a migração para **Débito Automático** para reduzir o atrito e as janelas de decisão de cancelamento.

---

## 🛠️ Tecnologias Utilizadas

* ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) **Python**: Linguagem principal.
* ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) **Pandas**: Manipulação de dados.
* ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) **NumPy**: Cálculos numéricos.
* ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) **Matplotlib**: Visualizações estáticas.
* ![Seaborn](https://img.shields.io/badge/Seaborn-4D88FF?style=for-the-badge&logo=python&logoColor=white) **Seaborn**: Visualizações estatísticas refinadas.
* ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white) **Plotly**: Dashboards interativos.
* ![Scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) **Scikit-learn**: Aprendizado de máquina.
* ![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white) **Google Colab**: Ambiente de desenvolvimento.

---

## 📂 Estrutura do Repositório

* `imagens/`: Gráficos gerados para o relatório.
* `TelecomX_BR.ipynb`: Código completo e análises.
* `TelecomX_Data`: Base de dados [Dados Fictícios]
* `TelecomX_dicionario`: Estrutura dos Dados
* `Relatório_TelecomX`: Relatório HTML
---

## 🚀 Como Executar
1. Clone o repositório.
2. Instale as dependências: `pip install pandas numpy matplotlib seaborn plotly scikit-learn`.
3. Execute o arquivo `TelecomX_BR.ipynb`.

---

**Desenvolvido por:** [Wagner Bruni Batista]  
**Contato:** [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/WBruni/analise-churn-telecom-x)
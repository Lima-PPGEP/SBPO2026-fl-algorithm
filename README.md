# SBPO 2026 - Federated Learning para Febre Amarela

## Sobre o Projeto

Este repositório contém o código-fonte e os dados utilizados no artigo submetido ao XLVII SBPO (Simpósio Brasileiro de Pesquisa Operacional), que compara algoritmos de Aprendizado Federado (FedAvg, FedProx, FedAvgM, FedAdam) na predição de óbito por febre amarela utilizando Regressão Logística.

## Base de Dados

- **Fonte:** SINAN/DATASUS - Febre Amarela (casos humanos, 1994-2025)
- **Download:** [Dados Abertos - Febre Amarela](https://dadosabertos.saude.gov.br/dataset/febre-amarela-em-humanos-e-primatas-nao-humanos)
- **Pré-processamento:**
  - Remoção de registros com `OBITO` = `IGN` (ignorado)
  - Codificação das variáveis para formato binário (0/1):
    - `SEXO_0_1`: 0 = Feminino, 1 = Masculino
    - `OBITO_0_1`: 0 = Não, 1 = Sim
- **Variáveis finais:**
  - Features: `IDADE`, `SEXO_0_1`
  - Target: `OBITO_0_1`
  - Cliente (para FL): `UF` (estado de infecção)

## Modelo - Regressão Logística

- **Biblioteca:** `scikit-learn` (LogisticRegression)
- **Pergunta de pesquisa:** *Idade e sexo influenciam o risco de óbito por febre amarela?*
- **Interpretação:** Odds Ratio para cada variável.

## Algoritmos de Aprendizado Federado

| Algoritmo | Descrição | Implementação |
|-----------|-----------|----------------|
| **FedAvg** | Média ponderada dos gradientes | Flower (FedAvg) |
| **FedProx** | Adiciona termo de proximidade (μ=0,1) | Flower (FedProx) |
| **FedAvgM** | FedAvg com momento (0,9) | Flower (FedAvgM) |
| **FedAdam** | Otimização adaptativa | Flower (FedAdam) |

## Estrutura do Repositório
```bash
SBPO2026-fl-algorithm/
├── data/
│   └── febre_amarela_casoshumanos.csv
├── images/                 
├── notebooks/
│   └── spbo2026_federated_learning.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

## Reprodutibilidade

Este repositório contém todos os elementos necessários para reproduzir os experimentos:

1. **Dados**: Arquivo CSV processado na pasta `data/`
2. **Código**: Jupyter Notebook em `notebooks/`
3. **Dependências**: `requirements.txt`


## Executando no VSCode

1. Clone o repositório:
   ```bash
   git clone https://github.com/Lima-PPGEP/SBPO2026-fl-algorithm.git
   cd SBPO2026-fl-algorithm
   ```

2. Crie e ative o ambiente virtual (Python 3.12):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. Instale as dependências:
   ```bash
   pip install -r requirements.txt
    ```

4. Execute o notebook spbo2026_federated_learning.ipynb.

## Executando no Google Colab

Para abrir diretamente no Google Colab clique aqui <a href="https://colab.research.google.com/github/Lima-PPGEP/SBPO2026-fl-algorithm/blob/main/notebooks/spbo2026_federated_learning.ipynb" target="_blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

Ou siga as instruções abaixo:

1. Faça o upload do notebook para o Google Colab ou abra diretamente:
   ```bash
   !git clone https://github.com/Lima-PPGEP/SBPO2026-fl-algorithm.git
   %cd SBPO2026-fl-algorithm
   ```

2. Instale a única biblioteca que não vem por padrão:
   ```bash
   !pip install flwr
    ```

3. As demais bibliotecas (pandas, numpy, scikit-learn, matplotlib) já estão pré-instaladas no Colab.
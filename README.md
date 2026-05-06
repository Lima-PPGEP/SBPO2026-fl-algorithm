# SBPO 2026 - Federated Learning para Febre Amarela

# Federated Learning para Febre Amarela

## Sobre o Projeto

Este repositório contém o código-fonte e os dados utilizados no artigo submetido ao XLVII SBPO, que compara algoritmos de Aprendizado Federado (FedAvg, FedProx, FedAvgM, FedAdam) na predição de óbito por febre amarela utilizando Regressão Logística.

## Base de Dados
- **Fonte:** SINAN/DATASUS - Febre Amarela (casos humanos, 1994-2025)
- **Download:** [Dados Abertos - Febre Amarela](https://dadosabertos.saude.gov.br/dataset/febre-amarela-em-humanos-e-primatas-nao-humanos)

## Bibliotecas Utilizadas
- `pandas`, `numpy` - Manipulação de dados
- `matplotlib` - Visualização
- `scikit-learn` - Regressão Logística
- `scipy` - Testes estatísticos
- `flwr[simulation]` - Aprendizado Federado

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

## Pré-requisitos

- Python 3.12, não utilizar versões superiores.
- VSCode com extensão Jupyter instalada

## Executando no VSCode
   - Verifique se o Python, Git, e o VSCode estão instalados antes de executar os passos abaixo.

1. Clone o repositório:
   ```bash
   git clone https://github.com/Lima-PPGEP/SBPO2026-fl-algorithm.git
   cd SBPO2026-fl-algorithm
   ```

2. Crie e ative o ambiente virtual:

   Windows
   ```bash
   py -3.12 -m venv venv
   venv\Scripts\activate     # Windows
   ```

   Linux
   ```bash
   python3.12 -m venv venv
   source venv/bin/activate
   ```

3. Instale as dependências:
   ```bash
   pip install -r requirements.txt
    ```

4. Após instalação, recarregue a janela do VSCode:
   - Ctrl+Shift+P → Developer: Reload Window

5. Em seguida selecione o interpretador no VSCode:
   - Ctrl+Shift+P → Python: Select Interpreter
   - Escolha o caminho onde o ambiente virtual: .\venv\Scripts\python.exe Ex.: SBPO2026-fl-algorithm\venv\Scripts\python.exe

6. Abra o notebook no VSCode:
   - Verifique se o Jupyter Notebook está utilizando o mesmo ambiente virtual (venv) para execução.
   - Faça isso clicando no canto superior direito do Jupyter Notebook deve estar escrito Python (descrição do ambiente virtual)

7. Execução:
   - Caso deseje execute todas as celulas do Jupyter Notebook utilize o botão Run All ou pressione Ctrl+F5.

## Nota sobre o Google Colab
O Colab não é recomendado para este notebook devido a conflitos de versão do Flower com as bibliotecas pré-instaladas. Utilize o ambiente local (VSCode) para reproduzir os experimentos.
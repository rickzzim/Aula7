# Aula 7
# Projeto de Filtros FIR e Processamento de Sinais de Áudio

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](COLOQUE_AQUI_O_LINK_DO_NOTEBOOK)

Este notebook explora o projeto e a aplicação de filtros FIR (Finite Impulse Response — Resposta ao Impulso Finita), abrangendo tanto aspectos teóricos quanto implementações práticas em processamento de sinais de áudio.

> Material desenvolvido para fins didáticos, no contexto de uma disciplina de Processamento Digital de Sinais.

## Sumário

- [Requisitos](#requisitos)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Como rodar o notebook](#como-rodar-o-notebook)
- [Conteúdo do notebook](#conteúdo-do-notebook)
  - [1. Fundamentos de Filtros FIR (Questão 1)](#1-fundamentos-de-filtros-fir-questão-1)
  - [2. Projeto Customizado de Filtro FIR (Questão 2)](#2-projeto-customizado-de-filtro-fir-questão-2)
  - [3. Filtragem de Sinal de Áudio (Questão 3)](#3-filtragem-de-sinal-de-áudio-questão-3)
- [Origem dos arquivos utilizados](#origem-dos-arquivos-utilizados)
- [Licença](#licença)

## Requisitos

- Python 3.x
- [numpy](https://numpy.org/)
- [scipy](https://scipy.org/)
- [matplotlib](https://matplotlib.org/)
- [IPython](https://ipython.org/) (para `IPython.display.Audio`)

Se for executar localmente (fora do Colab):

```bash
pip install numpy scipy matplotlib ipython
```

> No Colab, o upload do arquivo `handel.wav` é feito interativamente — veja [Como rodar o notebook](#como-rodar-o-notebook).

## Estrutura do repositório

```
.
├── notebook.ipynb        # Notebook principal
├── data/
│   └── handel.wav          # Áudio utilizado na Questão 3
└── README.md
```

> Ajuste os nomes/caminhos acima conforme a organização real do seu repositório.

## Como rodar o notebook

1. Abra o notebook no Google Colab.
2. Para a **Questão 3**, será necessário fazer upload do arquivo `handel.wav`. Execute a célula de código que contém:
   ```python
   from google.colab import files
   uploaded = files.upload()
   ```
   Uma caixa de diálogo permitirá selecionar o arquivo do seu computador.
3. Execute as células em sequência para ver os resultados, gráficos, métricas (SNR, MSE) e ouvir os exemplos de áudio.

## Conteúdo do notebook

### 1. Fundamentos de Filtros FIR (Questão 1)

- **Implementação manual de janelas:** funções para geração de diferentes tipos de janela (retangular, triangular, Hamming, Hann, Blackman).
- **Respostas ao impulso ideais:** implementação de respostas ao impulso ideais para diferentes tipos de filtro (passa-baixa, passa-alta, passa-faixa, rejeita-faixa).
- **Visualização:** gráficos demonstrando respostas ao impulso, diagramas de polos e zeros, e respostas em frequência para diferentes ordens de filtro e funções de janela.

### 2. Projeto Customizado de Filtro FIR (Questão 2)

- **Dedução de respostas ao impulso ideais:** derivações analíticas e implementações para formatos espectrais customizados:
  - Espectro em degraus (staircase)
  - Espectro triangular
  - Espectro trapezoidal
- **Análise e avaliação:** visualização das respostas ao impulso, diagramas de polos e zeros (com escala fixa para maior clareza), e respostas em frequência para esses filtros customizados, comparando os efeitos de diferentes funções de janela e ordens de filtro.

### 3. Filtragem de Sinal de Áudio (Questão 3)

- **Simulação do cenário:** introdução de um sinal de áudio real (`handel.wav`) contaminado com interferências tonais específicas (100 Hz, 2000 Hz) e ruído branco gaussiano.
- **Projeto de filtro FIR passa-faixa:** projeto e implementação manual de um filtro FIR passa-faixa para remover as interferências identificadas.
- **Avaliação de desempenho:**
  - **Comparações no domínio do tempo e da frequência:** análise visual dos sinais original, contaminado e recuperado.
  - **Métricas quantitativas:** cálculo da Relação Sinal-Ruído (SNR) e do Erro Quadrático Médio (MSE) para avaliar a eficácia da filtragem sob diferentes variâncias de ruído.
  - **Avaliação subjetiva do áudio:** reprodução dos sinais contaminado e recuperado para avaliação perceptual da remoção da interferência e da inteligibilidade do sinal.
- **Efeitos de quantização:** análise do impacto da quantização dos coeficientes (2, 4, 8, 16 bits) na resposta em frequência do filtro, demonstrando suas implicações práticas para implementações de DSP em ponto fixo.

## Origem dos arquivos utilizados

- `handel.wav`: arquivo de exemplo padrão (amplamente utilizado em material didático de processamento de sinais).

## Licença

Este projeto é disponibilizado **apenas para fins educacionais**. Não possui uma licença de código aberto formal — sinta-se à vontade para consultar o conteúdo como referência de estudo, mas reentre em contato antes de qualquer uso fora desse contexto.

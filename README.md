# Análise Histórica da Copa do Mundo e Redes de Relações com Gephi

## Objetivo do Projeto
Este projeto foi desenvolvido como parte de uma disciplina acadêmica com os seguintes objetivos:
1. Analisar os dados históricos da Copa do Mundo para identificar insights sobre o torneio, como desempenho de seleções, frequência de público e evolução histórica.
2. Modelar redes de relações entre seleções participantes, com pesos baseados em vitórias/derrotas e posições no pódio, e analisar essas redes utilizando o software Gephi.

---

## Estrutura do Projeto

### 1. Fontes e Preparação dos Dados
- **Fonte:** Dataset público do [Kaggle](https://www.kaggle.com/datasets/abecklas/fifa-world-cup), contendo informações sobre partidas, seleções, pódios, gols e público.
- **Etapas de Preparação:**
  - Remoção de linhas nulas e correção de caracteres inconsistentes.
  - Normalização de seleções (ex.: unificação das representações da Alemanha).
  - Junção de duas planilhas principais para análise e modelagem:
    - `WorldCupMatches.csv`: Dados de partidas.
    - `WorldCups.csv`: Dados de pódios.

### 2. Análises Realizadas
#### **Estatísticas Gerais e Insights**
- **Títulos por País:** Identificação dos países com mais títulos ao longo das edições.
- **Gols e Jogos:** Evolução do número de gols e partidas realizadas por edição.
- **Classificados e Público:**
  - Frequência de público ao longo do tempo.
  - Quantidade de times classificados por edição.
- **Curiosidades Identificadas:**
  - Top 10 partidas com maior público.
  - Top 10 estádios com maior média de público.
  - Top 20 seleções com mais gols totais.
  - Nuvem de palavras destacando os times com mais vitórias.

#### **Modelagem de Redes**
1. **Modelagem de Partidas:**
   - Rede direcionada com arestas representando "perdedor → vencedor".
   - Pesos das arestas baseados no número de vitórias (ex.: Brasil venceu a Alemanha 5 vezes, peso = 5).
   - Inclusão de empates como eventos únicos (160 empates).
   - Layout utilizado: Fruchterman-Reingold.
   - Métrica de centralidade: PageRank.

2. **Modelagem de Pódios:**
   - Rede com relações entre seleções com base nas colocações no pódio.
   - Pesos atribuídos conforme tabela de relevância:

| Colocações  | Peso  |
|-------------|-------|
| 1º - 2º     | 100%  |
| 2º - 3º     |  90%  |
| 3º - 4º     |  80%  |
| 1º - 3º     |  70%  |
| 2º - 4º     |  65%  |
| 1º - 4º     |  60%  |

### 3. Visualizações
Diversos gráficos foram criados para explorar os dados e facilitar a análise:
- **Gráficos Estatísticos:**
  - Barras, linhas e dispersão (matplotlib, seaborn, plotly).
  - Wordcloud destacando seleções com mais vitórias.
- **Visualizações de Redes:**
  - Redes de partidas e pódios no Gephi, utilizando layouts como Fruchterman-Reingold.

---

## Ferramentas Utilizadas
- **Bibliotecas Python:**
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - plotly
  - cufflinks
  - csv
  - wordcloud
- **Ambiente de Desenvolvimento:** Jupyter Notebook.
- **Software de Redes:** Gephi.

---

## Estrutura do Projeto no Repositório
- `social_media_analysis.ipynb`: Notebook utilizado na análise.
- `database/`: Arquivos CSV com os dados tratados e originais.
- `projeto-gephi.zip`: Arquivos de redes modeladas para visualização no Gephi.
- `Análise Histórica da Copa do Mundo (1930-2014).pdf`: Apresentação com gráficos gerados e nuvens de palavras.

---

## Como Reproduzir o Projeto
1. Clone o repositório para sua máquina local:
   ```bash
   git clone https://github.com/dotlincu/social-media-analysis
   ```
2. Instale as dependências necessárias:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o notebook Jupyter para replicar a análise.
4. Abra os arquivos de rede na pasta `projeto-gephi/` utilizando o Gephi para visualizar as redes modeladas.

---

## Futuras Melhorias
- Incluir dados de edições mais recentes da Copa do Mundo.
- Expandir a análise para contemplar estatísticas individuais de jogadores.
- Explorar mais métricas de redes no Gephi, como modularidade e centralidade de intermediação.

---

## Resultados e Conclusões
- **Insights Históricos:**
  - Identificação do domínio de algumas seleções (ex.: Brasil e Alemanha).
  - Aumento na diversidade de campeões em edições mais recentes.
- **Modelagem de Redes:**
  - Análise das redes destacou seleções centrais na história do torneio.
  - Rivalidades históricas identificadas por meio do PageRank e pesos das arestas.
- **Impacto Visual:**
  - As redes modeladas e os gráficos estatísticos proporcionaram uma visão clara das dinâmicas do torneio.


## Créditos
- **Dataset:** Disponível no [Kaggle](https://www.kaggle.com/datasets/abecklas/fifa-world-cup).
- **Autores:** 
    - [Lincoln Rebouças](https://www.linkedin.com/in/lincoln-reboucas/).
    - [Rafael Teixeira](https://www.linkedin.com/in/rafael-cteixeira/).
    - [Lucas Dias Leite](https://www.linkedin.com/in/lucas-dias-leite-a97534123/).

---

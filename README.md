# Previsão do valor de imóveis na Califórnia

Projeto final da disciplina **Aprendizado de Máquina Supervisionado** — MBA em Ciência de Dados, UNIFOR (Prof. Caio Ponte).

**Integrantes:** _(preencher nomes do grupo)_
**Vídeo de apresentação:** _(colar o link do YouTube)_

## Objetivo
Prever o **valor mediano das casas** (`median_house_value`) de regiões da Califórnia a partir de características como renda, localização, idade e tamanho dos domicílios. É um problema de **regressão supervisionada**.

## Dados
- Censo da Califórnia (1990): 20.640 regiões e 9 atributos (arquivo `california_house_price.csv`).
- Cada linha representa uma região (bloco censitário), não uma casa individual.

## Etapas do notebook
1. **Definição do problema** — contexto, dicionário de dados, features e target.
2. **Análise exploratória (EDA)** — distribuições, estatísticas descritivas, outliers, correlações, mapa geográfico e PCA.
3. **Pré-processamento** — limpeza, imputação (mediana), log e padronização, one-hot, criação de variáveis por domicílio e seleção de atributos, tudo em `Pipeline` (sem vazamento de dados).
4. **Treinamento** — Ridge, KNN, Árvore de Decisão, Random Forest e Gradient Boosting, com `GridSearchCV` e `RandomizedSearchCV` e validação cruzada (5 folds).
5. **Avaliação** — MAE, MSE, RMSE, R², MAPE e MedAE; benchmark entre os modelos, análise de erros, melhorias futuras e conclusão.

## Resultados (conjunto de teste)
| Modelo | RMSE (US$) | R² |
|---|---|---|
| **Gradient Boosting** | **40.609** | **0,825** |
| Random Forest | 43.904 | 0,795 |
| Árvore de Decisão | 51.077 | 0,723 |
| KNN | 51.349 | 0,720 |
| Ridge | 56.639 | 0,660 |
| Baseline (média) | 97.079 | 0,000 |

O melhor modelo (**Gradient Boosting**) erra em média cerca de **US$ 27 mil (≈ 16%)** e explica **82,5%** da variação dos preços.

## Como rodar
```bash
pip install -r requirements.txt
jupyter notebook projeto_final_regressao_california_didatico.ipynb
```
Mantenha o arquivo `california_house_price.csv` na mesma pasta do notebook e execute as células em ordem.

## Arquivos
- `projeto_final_regressao_california_didatico.ipynb` — notebook completo, com explicações.
- `projeto_final_regressao_california_didatico.pdf` — versão em PDF do notebook.
- `california_house_price.csv` — base de dados.
- `requirements.txt` — dependências.

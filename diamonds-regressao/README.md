# Diamonds: previsão de preços e otimização de hiperparâmetros

Estudo de regressão para estimar preços de diamantes a partir de suas características. Compara KNN e árvores de decisão e explora duas estratégias de ajuste de hiperparâmetros: busca em grade e evolução diferencial. Desenvolvido na disciplina de **Sistemas Inteligentes II**, da graduação em Engenharia da Computação da UEMG, em 2022.

## Objetivo

Preparar e explorar os dados, treinar modelos de regressão e comparar o desempenho obtido com diferentes configurações e estratégias de otimização.

## Dados

O código utiliza `diamonds.csv`, com atributos como peso em quilates, corte, cor, clareza e dimensões dos diamantes. A variável-alvo é **`price`**.

A versão descrita no relatório contém **53.940 registros** antes do tratamento. O arquivo de dados deve ser recuperado separadamente e precisa incluir as colunas esperadas pelo código, incluindo `Unnamed: 0` na versão original.

## Etapas implementadas

### Preparação e exploração

- Inspeção de tipos, valores ausentes e duplicidades.
- Remoção da coluna de índice `Unnamed: 0`.
- Remoção de registros com dimensão zero em `x`, `y` ou `z`.
- Estatísticas descritivas, matriz de correlação e gráficos de dispersão.
- Codificação de `cut`, `color` e `clarity` com LabelEncoder.
- Separação de atributos e variável-alvo.

### Modelagem

- **KNeighborsRegressor:** comparação de quantidades de vizinhos e formas de ponderação.
- **DecisionTreeRegressor:** comparação de profundidades da árvore.
- **GridSearchCV:** busca de combinações de hiperparâmetros com validação cruzada.
- **Evolução diferencial:** otimização com `scipy.optimize.differential_evolution`, usando MSE como função objetivo.
- **Avaliação:** R², MAE e MSE.

## Arquivos do estudo

| Arquivo | Conteúdo |
| --- | --- |
| `trabalho_2_sistemas_inteligentes_ii.py` | Experimentos com GridSearchCV, KNN e árvore de decisão. |
| `trabalho_3_sistemas_inteligentes_ii.py` | Retoma a etapa de GridSearchCV e acrescenta evolução diferencial. |
| `Relatorio_2_SI_II.pdf` | Relatório da etapa de GridSearchCV. |
| `diamonds.csv` | Base esperada pelo código; deve ser disponibilizada separadamente. |

## Tecnologias

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn e SciPy.

## Execução

Notebooks originais:

- [GridSearchCV](https://colab.research.google.com/drive/1r3shxwg3weZJqCV1PTydaiBuBEYXn4L1).
- [Evolução diferencial](https://colab.research.google.com/drive/1qc2yJgaaSkzaewH6gcgrzwROeOYI1j8y).

1. Abra o notebook escolhido ou copie o respectivo código para células do Colab.
2. Disponibilize `diamonds.csv` no diretório de trabalho.
3. Instale as dependências, caso necessário:

   ```python
   %pip install pandas numpy matplotlib seaborn scikit-learn scipy
   ```

4. Execute primeiro a preparação dos dados e depois a etapa de modelagem.
5. Confira o custo computacional antes de executar todas as repetições. Se alterar a quantidade de execuções, registre essa mudança ao apresentar os resultados.

## Resultados e escopo

Na tabela do relatório de GridSearchCV, a árvore de decisão apresentou **R² de aproximadamente 0,9654** e **MAE de aproximadamente 364,23** em uma das execuções registradas. Esses valores são resultados históricos do relatório, e não uma nova medição da versão atual do código.

O relatório apresenta duas repetições, enquanto os scripts configuram 30 na etapa de GridSearchCV. Embora o código use K-fold para a busca de hiperparâmetros, a avaliação externa utiliza apenas a última divisão do laço; não corresponde à média de todos os folds externos.

Na etapa de evolução diferencial, o arquivo de dados é carregado novamente e recebe um pré-processamento diferente. Para uma comparação consistente entre estratégias, uma revisão futura deve uniformizar a preparação dos dados e as divisões de avaliação.

## Autora

Sofia Anita Miranda — Engenharia da Computação, UEMG.

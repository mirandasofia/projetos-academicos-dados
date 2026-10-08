# Redes neurais aplicadas a dados de Covid e saúde cardiovascular

Estudos acadêmicos de regressão e classificação com dados de saúde, desenvolvidos na disciplina de **Redes Neurais Artificiais**, da graduação em Engenharia da Computação da UEMG, em 2022.

## Objetivo

Comparar funções de ativação e quantidades de neurônios em duas tarefas: estimar mortes semanais por Covid e classificar registros quanto à presença de doença cardiovascular.

## Experimentos

| Estudo | Dados | Variável-alvo | Modelo | Métrica |
| --- | --- | --- | --- | --- |
| Covid Brasil | `covidBrasil.csv` | `Weekly Deaths` | ELMRegressor | R². |
| Classificação cardiovascular | `cardio_train.csv` | `cardio` | MLPClassifier | Acurácia. |

### Covid Brasil

O arquivo contém indicadores relacionados a casos, mortes e vacinação. O código separa `Weekly Deaths` como variável-alvo e utiliza as demais colunas como entrada.

São comparadas seis configurações de ELMRegressor, combinando **50, 75 e 100 neurônios** com as funções **ReLU e tanh**. A avaliação utiliza holdout, com 25% dos registros para teste, e a métrica R².

### Classificação cardiovascular

A base contém características como idade, medidas corporais, pressão arterial, colesterol, glicose e hábitos dos pacientes.

O código lê o arquivo com separador `;`, remove a coluna `id` e seleciona uma amostra aleatória de **10 mil registros**. A variável-alvo é `cardio`.

São comparadas seis configurações de MLPClassifier, com **50, 75 e 100 neurônios** e funções **ReLU e tanh**. A avaliação também utiliza holdout com 25% dos registros para teste, acompanhando a acurácia.

## Arquivos do estudo

| Arquivo | Conteúdo |
| --- | --- |
| `trabalho_rna_2_parte_1_(covidbrasil).py` | Regressão com a base Covid Brasil. |
| `trabalho_rna_2_2º_parte_(cardio_train).py` | Classificação com a base cardiovascular. |
| `Relatorio_Trabalho_2___RNA.pdf` | Relatório dos dois estudos: Covid na seção 2 e cardiovascular na seção 3. |
| `covidBrasil.csv` e `cardio_train.csv` | Bases esperadas pelos códigos; devem ser disponibilizadas separadamente. |

## Tecnologias

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn e [Scikit-ELM](https://github.com/akusok/scikit-elm).

## Execução

Notebooks originais:

- [Covid Brasil](https://colab.research.google.com/drive/1CYEAgBHkt3AhFskso47j4hK2m9mx9Rot).
- [Classificação cardiovascular](https://colab.research.google.com/drive/1MllsbdEoRrTi6wgQQo-ML-YNOoEKTp3J).

1. Abra o notebook desejado ou copie o código correspondente para células do Colab.
2. Disponibilize o arquivo de dados no diretório de trabalho.
3. Instale as dependências, caso necessário:

   ```python
   %pip install pandas numpy matplotlib seaborn scikit-learn scikit-elm
   ```

4. Execute as células na ordem original e confira as métricas de cada configuração.

O comando `!pip install scikit-elm` da exportação de Covid é próprio de notebook e precisa ser separado do código se a execução for feita como script Python comum.

## Resultados e escopo

O relatório registra desempenho variável entre as configurações: resultados insatisfatórios para parte dos modelos ELM e acurácias próximas de 50% no estudo cardiovascular. Os experimentos documentam a comparação de modelos e a identificação de limitações, sem demonstrar um modelo validado para uso clínico.

No estudo de Covid, a divisão de treino e teste é aleatória. A interpretação dos resultados deve considerar a ordem temporal dos dados e quais variáveis estariam disponíveis no momento de uma previsão. A quantidade de registros apresentada no relatório também precisa ser conferida na base original.

Na classificação cardiovascular, a seleção das 10 mil amostras e os modelos MLP não possuem semente explícita, o que pode alterar os resultados entre execuções.

## Autora

Sofia Anita Miranda — Engenharia da Computação, UEMG.

# Redes neurais aplicadas à classificação de crédito e previsão de preços

Dois experimentos de aprendizado supervisionado para comparar configurações de redes neurais em tarefas distintas: classificação de clientes para concessão de crédito e regressão de preços de diamantes. Desenvolvidos na disciplina de **Redes Neurais Artificiais**, da graduação em Engenharia da Computação da UEMG, em 2022.

## Objetivo

Investigar o efeito da quantidade de neurônios e da função de ativação no desempenho de modelos MLP e ELM, utilizando preparação de dados e avaliação em conjuntos de teste.

## Experimentos

| Estudo | Dados | Variável-alvo | Modelo | Métrica |
| --- | --- | --- | --- | --- |
| Classificação de clientes | `credtrain.txt` | `Classe` | MLPClassifier | Acurácia. |
| Previsão de preços de diamantes | `diamonds.csv` | `price` | ELMRegressor | R². |

### Classificação de clientes

O estudo utiliza uma base acadêmica de crédito de uma instituição fictícia, com atributos socioeconômicos e informações de financiamento. O código nomeia as colunas, verifica valores ausentes e separa a variável `Classe` dos atributos de entrada.

São comparadas seis configurações de MLPClassifier, combinando **50, 75 e 100 neurônios** com as funções de ativação **ReLU e tanh**. A divisão em treino e teste é realizada por holdout, com 25% dos registros destinados ao teste.

### Previsão de preços de diamantes

A preparação dos dados inclui remoção da coluna de índice, exclusão de registros com dimensões zero e codificação de corte, cor e clareza com LabelEncoder.

São comparadas seis configurações de ELMRegressor, também combinando **50, 75 e 100 neurônios** com **ReLU e tanh**. O desempenho é avaliado por R² após uma divisão holdout com 25% dos registros para teste.

## Arquivos do estudo

| Arquivo | Conteúdo |
| --- | --- |
| `trabalho_1_rna.py` | Classificação de clientes com MLP. |
| `trabalho_rna_1_parte_2.py` | Regressão de preços de diamantes com ELM. |
| `Relatorio_Trabalho_1___RNA.pdf` | Relatório dos dois experimentos: crédito na seção 2 e diamantes na seção 3. |
| `credtrain.txt` e `diamonds.csv` | Bases esperadas pelos códigos; devem ser disponibilizadas separadamente. |

O arquivo de crédito é lido como texto sem cabeçalho, com campos separados por espaços. A versão de Diamonds precisa corresponder ao esquema utilizado pelo script.

## Tecnologias

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn e [Scikit-ELM](https://github.com/akusok/scikit-elm).

## Execução

Notebooks originais:

- [Classificação de crédito](https://colab.research.google.com/drive/1IaCqi6h9DJBv62Lr59chRaub_gVKVWWH).
- [Regressão de diamantes](https://colab.research.google.com/drive/1TsXXCS6dwUOO-uVgQTVa9k7EiL2EAAOS).

1. Abra o notebook do experimento desejado ou copie o código para células do Colab.
2. Disponibilize a base correspondente no diretório de trabalho.
3. Instale as dependências, caso necessário:

   ```python
   %pip install pandas numpy matplotlib seaborn scikit-learn scikit-elm
   ```

4. Execute as células na ordem original e compare as métricas das seis configurações.

Os comandos `!pip install scikit-elm` presentes no código exportado pertencem ao ambiente de notebook. Para transformar a exportação em um script `.py` comum, a instalação deve ficar separada do código Python.

## Resultados e escopo

O relatório apresenta os resultados das seis configurações de cada estudo e permite observar a influência da arquitetura e da ativação nas métricas. Algumas configurações de ELM com tanh apresentaram R² negativo, indicando que os resultados variaram significativamente entre as alternativas testadas.

Na classificação de crédito, o código calcula versões padronizadas dos dados, mas treina os modelos com os dados originais. A avaliação implementada é holdout; a importação de LeaveOneOut não corresponde ao procedimento efetivamente utilizado. As redes não possuem semente explícita, portanto novas execuções podem produzir resultados diferentes.

## Autora

Sofia Anita Miranda — Engenharia da Computação, UEMG.

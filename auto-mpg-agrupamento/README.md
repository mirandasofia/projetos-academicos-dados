# Auto MPG: análise exploratória e agrupamento de veículos

Estudo acadêmico sobre a relação entre o peso de automóveis e seu consumo de combustível, com análise exploratória e experimentação de agrupamentos por K-means. Desenvolvido na disciplina de **Sistemas Inteligentes II**, da graduação em Engenharia da Computação da UEMG, em 2022.

## Objetivo

Explorar características dos veículos, preparar os dados para análise e comparar diferentes quantidades de grupos utilizando o índice Davies-Bouldin.

## Dados

A base **Auto MPG**, disponibilizada pelo [UCI Machine Learning Repository](https://www.archive.ics.uci.edu/dataset/9/auto%2Bmpg), contém informações sobre consumo de combustível e características de automóveis.

O código utiliza um arquivo chamado `auto-mpg.csv`. A versão em CSV precisa ser recuperada ou preparada com as colunas esperadas pelo script. Os atributos centrais para a análise exploratória são:

| Atributo | Significado | Conversão aplicada |
| --- | --- | --- |
| `weight` | Peso do veículo, em libras. | Conversão para quilogramas. |
| `mpg` | Consumo em milhas por galão. | Conversão para quilômetros por litro. |

## Etapas implementadas

1. Leitura e inspeção dos dados com Pandas.
2. Cálculo de estatísticas descritivas, incluindo média, desvio padrão e variância.
3. Verificação de valores ausentes e registros duplicados.
4. Remoção da coluna `horsepower` e conversão de unidades.
5. Visualização da relação entre peso e consumo.
6. Agrupamento com K-means e visualização dos grupos.
7. Comparação de configurações de 2 a 10 grupos pelo índice Davies-Bouldin.

## Arquivos do estudo

| Arquivo | Conteúdo |
| --- | --- |
| `trabalho_1_de_sistemas_inteligentes_ii.py` | Código exportado do Google Colab. |
| `Relatorio_SI_II.pdf` | Relatório acadêmico com metodologia, figuras e resultados. |
| `auto-mpg.csv` | Base esperada pelo código; deve ser disponibilizada separadamente. |

O arquivo `Relatorio_SI_II (1).pdf` é uma cópia idêntica do relatório; basta manter uma versão.

## Tecnologias

Python, Pandas, NumPy, Matplotlib, Seaborn e Scikit-learn.

## Execução

O ambiente original foi o [Google Colab](https://colab.research.google.com/drive/1NTZJbj_O5vgfwVOhkAK6SnZ-I5ow92HO).

1. Abra o notebook original ou copie o código para células de um novo notebook.
2. Disponibilize `auto-mpg.csv` no diretório de trabalho do notebook, normalmente `/content`.
3. Instale as dependências em uma célula, caso necessário:

   ```python
   %pip install pandas numpy matplotlib seaborn scikit-learn
   ```

4. Execute as células na ordem original e confira as tabelas, figuras e valores de Davies-Bouldin.

## Resultados e escopo

O relatório registra a configuração com **quatro grupos** como a melhor entre as avaliadas, com índice Davies-Bouldin de aproximadamente **0,4839**. Valores menores desse índice indicam melhor separação dos grupos segundo esse critério, conforme a [documentação do Scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.davies_bouldin_score.html).

A versão exportada do código realiza o agrupamento usando apenas `weight`; `mpg` participa da análise exploratória. O script calcula uma versão padronizada do peso, mas não a utiliza no treinamento do K-means. Essas características devem ser consideradas ao comparar a implementação com a descrição do relatório e ao planejar novos experimentos.

## Autora

Sofia Anita Miranda — Engenharia da Computação, UEMG.

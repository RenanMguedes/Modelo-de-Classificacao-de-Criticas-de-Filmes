# Modelo-de-Classificacao-de-Criticas-de-Filmes

O objetivo do trabalho foi desenvolver um modelo capaz de classificar reviews de filmes como positivas ou negativas. Adotei a 
abordagem de aplicação de processamento de linguagem natural 
(NLP) e utilização de conceitos da matéria como PCA, SVD e 
regressão logística.

Extraí o dataset do IMDB através do site kaggle, e na tabela há 4 
colunas, um ID, review em inglês, review em português e o 
sentimento(“pos” para positivo e “neg” para negativo) e com isso 
extraímos apenas as colunas da review em portugues e o sentimento. O link do dataset é https://www.kaggle.com/datasets/anairamcosta/imdb-reviews-pt-br-csv

Após a obtenção dos dados, utilizei esses teoremas e tecnologias:

#### Modelagem Vetorial com TF-IDF (NLP): 
A técnica Term Frequency-Inverse Document Frequency foi utilizada para estruturar os dados não estruturados. Isso converteu os textos em uma Matriz Termo-Documento, onde cada vetor representa a relevância estatística das palavras, criando a base para o Reconhecimento de Padrões.

#### Decomposição em Valores Singulares (SVD):A tecnologia central do trabalho foi a fatoração matricial $A = U\Sigma V^{\top}$, implementada com numpy. Calculei explicitamente os vetores singulares para isolar a estrutura semântica latente dos ruídos linguísticos.

#### Análise Espectral e Redução de Dimensionalidade:
A seleção da dimensão $k$ foi governada através do Cálculo da Norma de Frobenius ($\|A\|_F^2 = \sum \sigma_i^2$) para quantificar a informação total da matriz. Utilizei também a curva de variância acumulada para determinar a melhor Aproximação de Posto Baixo, garantindo que o subespaço vetorial escolhido preservasse a variância necessária para a classificação, descartando dimensões de ruído.

#### Classificação via Modelos Aproximados:
Para a predição final, usei Regressão Logística. O modelo foi treinado para otimizar uma fronteira de decisão (função sigmoide) dentro do espaço reduzido pelo SVD, aprendendo a distinguir a polaridade dos vetores geométricos resultantes com alta eficiência computacional.

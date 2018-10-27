# Pré-Processamento Escala,Normalizacao,Padronizacao e Binarizacao

## Preparando os Dados para Machine Learning:

 - Muitos algoritmos esperam receber os dados em um formato específico. É seu trabalho preparar os dados em uma estrutura que seja adequada ao algoritmo que você está utilizando.

 - É muito provável que você tenha que realizar tarefas de pré-processamento nos dados. Esse é um passo necessário dentro do processo. O desafio é o fato que cada algoritmo requer uma estrutura diferente, o que pode requerer transformações diferentes nos dados. Mas é possível em alguns casos, obter bons resultados sem um trabalho de pré-processamento. Mas é uma boa prática criar diferentes visões e transformações dos dados, de modo a poder testar diferentes algoritmos de Machine Learning.

1. Escala
 - E uma das primeiras tarefas dentro do pré-processamento, é colocar seus dados na mesma escala. Muitos algoritmos de Machine Learning vão se beneficiar disso e produzir resultados melhores. Esta etapa também é chamada de normalização e significa colocar os dados em uma escala com range entre 0 e 1. Isso é útil para a otimização, sendo usado no core dos algoritmos de Machine Learning, como gradient descent. Isso também é útil para algoritmos como regressão e redes neurais e algoritmos que usam medidas de distância, como KNN. O scikit-learn possui uma função para esta etapa, chamada MinMaxScaler().

```python
    # Transformando os dados para a mesma escala (entre 0 e 1)

    # Import dos módulos
    from pandas import read_csv
    from sklearn.preprocessing import MinMaxScaler

    # Carregando os dados
    url = "http://datascienceacademy.com.br/blog/aluno/Python-Spark/Datasets/pima-data.csv"
    colunas = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class']
    df = read_csv(url, names = colunas)
    array = df.values

    # Separando o array em componentes de input e output
    X = array[:,0:8]
    Y = array[:,8]

    # Gerando a nova escala
    scaler = MinMaxScaler(feature_range = (0, 1))
    rescaledX = scaler.fit_transform(X)

    # Sumarizando os dados transformados
    print(rescaledX[0:5,:])
```

2. Padronizacao

• Padronização é a técnica para transformar os atributos com distribuição Gaussiana (normal) e diferentes médias e desvios padrões em uma distribuição Gaussiana com a média igual a 0 e desvio padrão igual a 1. Isso é útil para algoritmos que esperam que os dados estejam com uma distribuição Gaussiana, como regressão linear, regressão logística e linear discriminant analysis. Funciona bem quando os dados já estão na mesma escala. O scikit-learn possui uma função para esta etapa, chamada StandardScaler().

```python
    # Padronizando os dados (0 para a média, 1 para o desvio padrão)

    # Import dos módulos
    from pandas import read_csv
    from sklearn.preprocessing import StandardScaler

    # Carregando os dados
    url = "http://datascienceacademy.com.br/blog/aluno/Python-Spark/Datasets/pima-data.csv"
    colunas = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class']
    df = read_csv(url, names = colunas)
    array = df.values

    # Separando o array em componentes de input e output
    X = array[:,0:8]
    Y = array[:,8]

    # Gerando o novo padrão
    scaler = StandardScaler().fit(X)
    standardX = scaler.transform(X)

    # Sumarizando os dados transformados
    print(standardX[0:5,:])
```


3. Normalização

• No scikit-learn, normalização se refere a ajustar a escala de cada observação (linha) de modo que ela tenha comprimento igual a 1 (chamado vetor de comprimento 1 em álgebra linear). Este método de pré-processamento é útil quando temos datasets esparsos (com muitos zeros) e atributos com escala muito variada. Útil quando usamos algoritmos de redes neurais ou que usam medida de distância, como KNN. O scikit-learn possui uma função para esta etapa, chamada Normalizer().

```python
    # Normalizando os dados (comprimento igual a 1)
    from pandas import read_csv
    from sklearn.preprocessing import Normalizer

    # Carregando os dados
    url = "http://datascienceacademy.com.br/blog/aluno/Python-Spark/Datasets/pima-data.csv"
    colunas = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class']
    df = read_csv(url, names = colunas)
    array = df.values

    # Separando o array em componentes de input e output
    X = array[:,0:8]
    Y = array[:,8]

    # Gerando os dados normalizados
    scaler = Normalizer().fit(X)
    normalizedX = scaler.transform(X)

    # Sumarizando os dados transformados
    print(normalizedX[0:5,:])
```

4. Transformar os Dados em Valores Binários (Binarizing)

• Nós podemos definir um valor em nossos dados, ao qual chamamos de threshold e então definimos que todos os valores acima do threshold serão marcados como sendo 1 e todos valores iguais ou abaixo do threshold serão marcados como sendo 0. Isso é o que chamamos de Binarizing. Isso é útil quando temos probabilidades e queremos transformar os dados em algo com mais significado. O scikit-learn possui uma função para esta etapa, chamada Binarizer().

```python
    # Binarização

    # Import dos módulos
    from pandas import read_csv
    from sklearn.preprocessing import Binarizer

    # Carregando os dados
    url = "http://datascienceacademy.com.br/blog/aluno/Python-Spark/Datasets/pima-data.csv"
    colunas = ['preg', 'plas', 'pres', 'skin', 'test', 'mass', 'pedi', 'age', 'class']
    df = read_csv(url, names = colunas)
    array = df.values

    # Separando o array em componentes de input e output
    X = array[:,0:8]
    Y = array[:,8]

    # Gerando a binarização
    binarizer = Binarizer(threshold = 0.0).fit(X)
    binaryX = binarizer.transform(X)

    # Sumarizando os dados transformados
    print(binaryX[0:5,:])
```
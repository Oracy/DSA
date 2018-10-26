# Analise Exploratoria Seaborn:

1. Pairplot
```python
    sns.pairplot(dados)
```


2. Boxplot com orientação vertical
```python
    sns.boxplot(data = dados, orient = "v")
```


3. Clustermap
```python
    sns.clustermap(dados)
```


4. describe
```python
    dados.describe
```


5. kdeplot
```python
    sns.kdeplot(dados.age,dados.mass)
```

6. distplot
```python
    from scipy import stats
    sns.distplot(dados.pedi, fit = stats.norm);
```
---

## Preparando os Dados para Machine Learning:
 - Muitos algoritmos esperam receber os dados em um formato específico. É seu trabalho preparar os dados em uma estrutura que seja adequada ao algoritmo que você está utilizando.

 - É muito provável que você tenha que realizar tarefas de pré-processamento nos dados. Esse é um passo necessário dentro do processo. O desafio é o fato que cada algoritmo requer uma estrutura diferente, o que pode requerer transformações diferentes nos dados. Mas é possível em alguns casos, obter bons resultados sem um trabalho de pré-processamento. Mas é uma boa prática criar diferentes visões e transformações dos dados, de modo a poder testar diferentes algoritmos de Machine Learning.

## Escala
 - E uma das primeiras tarefas dentro do pré-processamento, é colocar seus dados na mesma escala. Muitos algoritmos de Machine Learning vão se beneficiar disso e produzir resultados melhores. Esta etapa também é chamada de normalização e significa colocar os dados em uma escala com range entre 0 e 1. Isso é útil para a otimização, sendo usado no core dos algoritmos de Machine Learning, como gradient descent. Isso também é útil para algoritmos como regressão e redes neurais e algoritmos que usam medidas de distância, como KNN. O scikit-learn possui uma função para esta etapa, chamada MinMaxScaler().
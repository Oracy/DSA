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

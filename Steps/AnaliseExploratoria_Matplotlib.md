# Analise Exploratoria Matplotlib:

Graficos menores podem ser exibidos no mesmo arquivo do jupyter notebook, pois ocupam menos espacos, agora para grandes conjuntos de graficos a linha abaixo deve ser comentada ou retirada, para que seja criado graficos em uma janela nova, como codigo abaixo:
```python
#%matplotlib inline
```


1. Histograma Univariado

```python
    dados.hist()
    plt.show()
```

• Com o histograma podemos rapidamente avaliar a distribuição de cada atributo. Os histograma agrupam os dados em bins e fornecem uma contagem do número de observações em cada bin. Com o histograma, você pode rapidamente verificar a simetria dos dados e se eles estão em distribuição normal ou não. Isso também vai ajudar na identificação dos outliers.

• Podemos ver que os atributos age, pedi e test possuem uma distribuição exponencial. Podemos ver que as colunas mass e press possuem uma distribuição normal.


2. Density Plot Univariado
```python
    dados.plot(kind = 'density', subplots = True, layout = (3,3), sharex = False)
    plt.show()
```
• Os Density Plots são outra forma de visualizar a distribuição dos dados para cada atributo. O plot é como uma espécie de histograma abstrato com uma curva suave através do topo dos bins de um histograma. Pode ser mais fácil identificar a distribuição dos dados usando um density plot.


3. Box and Whisker Plots
```python
    dados.plot(kind = 'box', subplots = True, layout = (3,3), sharex = False, sharey = False)
    plt.show()
```

• Com os boxplots também podemos revisar a distribuição dos dados para cada atributo. A linha no centro (vermelho) é o valor da mediana (quartil 50%), a linha abaixo é o quartil 25% e a linha acima o quartil 75%. O boxplot ajuda a ter uma ideia da dispersão dos dados e os possíveis outliers.

Podemos ver que a dispersão dos dados é bem diferente entre os atributos. As colunas age, skin e test possuem uma simetria muito próxima a valores de dados menores.


4. Matriz de Correlação com nomes das variáveis
```python
    correlations = dados.corr()
```
- Plot
```python
    import numpy as np
    fig = plt.figure()
    ax = fig.add_subplot(111)
    cax = ax.matshow(correlations, vmin = -1, vmax = 1)
    fig.colorbar(cax)
    ticks = np.arange(0, 9, 1)
    ax.set_xticks(ticks)
    ax.set_yticks(ticks)
    ax.set_xticklabels(colunas)
    ax.set_yticklabels(colunas)
    plt.show()
```


5. Matriz de Correlação genérica
```python
    correlations = dados.corr()
```

- Plot
```python
    fig = plt.figure()
    ax = fig.add_subplot(111)
    cax = ax.matshow(correlations, vmin = -1, vmax = 1)
    fig.colorbar(cax)
    plt.show()
```

6. Scatter Plot
```python
    from pandas.plotting import scatter_matrix
    scatter_matrix(dados)
    plt.show()
```

• Um scatterplot mostra o relacionamento entre duas variáveis como pontos em duas dimensões, sendo um eixo para cada variável. Podemos criar um scatterplot para cada par de variáveis em nosso dataset. A exemplos da matriz de correlação, o scatterplot matrix é simétrico.
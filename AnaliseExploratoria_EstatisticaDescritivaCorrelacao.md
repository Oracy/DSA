# Analise Exploratoria Estatistica Descritiva e Correlacao:

1. Visualizando as primeiras 20 linhas:

```python
    dados.head(20)
```

• Se o número de linhas no seu arquivo for muito grande, o algoritmo pode levar muito tempo para ser treinado. Se o número de registros for muito pequeno, você pode não ter registros suficientes para treinar seu modelo.

• Se você tiver muitas colunas em seu arquivo, o algoritmo pode apresentar problemas de performance devido a alta dimensionalidade.

• A melhor solução vai depender de cada caso. Mas lembre-se: treine seu modelo em um subset do seu conjunto maior de dados e depois aplique o modelo no Big Data.


2. Visualizando as dimensões

```python
    dados.shape
```

3. Tipo de dados de cada atributo
    
```python
    dados.dtypes
```
• O tipo dos dados é muito importante. Pode ser necessário converter strings ou colunas com números inteiros podem representar variáveis categóricas ou valores ordinários.


4. Sumário estatístico
    
```python
    dados.describe()
```

5. Distribuição das classes

```python
    dados.groupby('class').size()
```
• Em problemas de classificação pode ser necessário balancear as classes. Classes desbalanceadas (ou seja, volume maior de um dos tipos das classes) são comuns e precisam ser tratadas durante a fase de pré-processamento. Podemos ver abaixo que existe uma clara desproporção entre as classes 0 (não ocorrência de diabetes) e 1 (ocorrência de diabetes).


6. Correlação de Pearson
    
```python
    dados.corr(method = 'pearson')
```
• A correlação é o relacionamento entre 2 variáveis. O métodos mais comum para calcular correlação é o método de Pearson, que assume uma distribuição normal dos dados. Correlação de -1 mostra uma correlação negativa, enquanto uma correlação de +1 mostra uma correlação positiva. Uma correlação igual a 0 mostra que não há relacionamento entre as variáveis.

• Alguns algoritmos como regressão linear e regressão logística podem apresentar problemas de performance se houverem atributos altamente correlacionados (colineares).


7. Verificando o skew de cada atributo
    
```python
    dados.skew()
```
• Skew (ou simetria) se refere a distribuição dos dados que é assumida ser normal ou gaussiana (bell curve). Muitos algoritmos de Machine Learning consideram que os dados possuem uma distribuição normal. Conhecendo a simetria dos dados, permite que você faça uma preparação e entregue o que o algoritmo espera receber, aumentado desta forma a acurácia do modelo preditivo.
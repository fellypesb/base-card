# Base Card

Neste estudo buscou-se realizar a comparação de resultados obtidos com uma mesma base de dados ordenada de 3 formas diferentes. Para isso aplicou-se diferentes modelos de aprendizado de máquina juntamente com a técnica de validação cruzada ou _cross validation_ com 10 _k-folds_.

Quatro modelos foram escolhidos para este estudo, foram eles:
- KNN
- Random Forest
- Naive Bayes
- Neural Network

## Análise inicial dos dados

Ao realizar a análise inicial da base de dados utilizada foram encontradas dois atributos, coluna 10 e 50, sem variação em suas instâncias. Dessa forma, estes atributos não fornecem nenhuma informação relevante para os modelos uma vez que apresentam um único valor em suas instâncias, por isso, optou-se por descartar estes atributos do conjunto de entradas.

## Orange _workflow_

Utilizando-se do software orange criou-se um pequeno _workflow_ de trabalho formado pelos widgets: _File_, _Data Table_, _widgets_ dos modelos, _Test and Score_, _Confusion Matrix_ e _Predictions_. Como apresentado na figura abaixo. Criou-se este mesmo _worklflow_ para cada uma das base de dados.

<center> <img src="https://uploaddeimagens.com.br/images/004/297/354/full/orange_worflow.png?1673572776" width="430"/> </center>

## Resultados

Em todas as variações da base de dados o modelo de melhor e pior desempenho se mantiveram os mesmos. O modelo de melhor desempenho foi o _Random Forest_ e o modelo de pior desempenho foi o KNN como pode ser constatado pelas métricas: AUC, CA, F1, _Precision_ e _Recall_ que são apresentado nas tabelas a seguir. Além disso, em todas as comparações o modelo _Random Forest_ apresentou maior probabilidade de ter desempenho superior aos demais modelos.

### Resultados para base de dados 1

Modelo |AUC|CA|F1|Precision|Recall| 
----------------|:-------:|:-------:|:-------:|:-------:|:-------:|
Random Forest   | 0.920 | 0.872 | 0.873 | 0.873 | 0.872 |
Neural Network  | 0.896 | 0.852 | 0.852 | 0.853 | 0.852 |
Naive Bayes     | 0.890 | 0.816 | 0.816 | 0.816 | 0.816 |
kNN             | 0.685 | 0.638 | 0.636 | 0.635 | 0.638 |

### Resultados para base de dados 2
Modelo |AUC|CA|F1|Precision|Recall| 
----------------|:-------:|:-------:|:-------:|:-------:|:-------:|
Random Forest   | 0.907 | 0.851 | 0.851 | 0.851 | 0.851 |
Neural Network  | 0.891 | 0.848 | 0.848 | 0.850 | 0.848 |
Naive Bayes     | 0.889 | 0.814 | 0.815 | 0.815 | 0.814 |
kNN             | 0.679 | 0.657 | 0.654 | 0.654 | 0.657 |

### Resutados para base de dados 3
Modelo |AUC|CA|F1|Precision|Recall| 
-------|:---:|:--:|:--:|:---------:|:------:|
Random Forest   | 0.905 | 0.852 | 0.852 | 0.852 | 0.852 |
Neural Network  | 0.893 | 0.848 | 0.848 | 0.848 | 0.848 |
Naive Bayes     | 0.890 | 0.819 | 0.819 | 0.819 | 0.819 |
kNN             | 0.692 | 0.648 | 0.644 | 0.645 | 0.648 |

Como pode ser observado nos resultados acima praticamente não houve grandes diferenças nos resultados obtidos para as 3 base de dados. Isso nos leva a supor que o ordenamento dos dados não é relevante para melhorar ou piorar o desempenho dos modelos ou alterá-lo de forma significativa.

Abaixo também são apresentadas as matrizes de confusão do melhor modelo treinado, _Random Forest_, para as 3 base de dados. Nestas matrizes pode-se constatar a menor quantidade de erros nas predições deste modelo. 

### Matriz de confusão - Base de dados 1

x | 0 | 1 | $$\sum$$ |
---|-----|------|-----|
0|338|45| 338 |
1|43|264| 307 |
$$\sum$$| 381 | 309 | 690 |

### Matriz de confusão - Base de dados 2

x | 0 | 1 | $$\sum$$ |
---|-----|------|-----|
0|331|52| 383 |
1|51|256| 307 |
$$\sum$$| 382 | 308 | 690 |

### Matriz de confusão - Base de dados 3

x | 0 | 1 | $$\sum$$ |
---|-----|------|-----|
0|333|50| 388 |
1|52| 255 | 307 |
$$\sum$$| 385 | 305 | 690 |







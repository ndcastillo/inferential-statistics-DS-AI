El coeficiente de Pearson es una **covarianza estandarizada** entre dos valores, con obtenemos cuanto se afecta dos variables entre si, para el cálculo del coeficiente de Pearson poblacional $r$ esta determinada por:

$$
r = \frac{Cov(X,Y)}{\sigma_x \sigma_y}
$$

## Características del coeficiente de Pearson

Los valores del coeficientes de Pearson se encuentran entre (-1,+1), donde +1 indica la correlación lineal positiva perfecta y -1 es una correlación lineal negativa perfecta. Para obtener este coeficiente utilizamos el modulo de `scipy.stats` y el método de `.pearsonr()`. Entonces:

```
scipy.stats.pearsonr(A,B)
```

Siendo A y B dataframes de caracter pandas.El número obtenido a travez de esta codificación, podriamos interpretarla con la siguiente tabla:

| Coeficiente | Grado de Correlación | Tipo de Correlación |
| ----------- | -------------------- | ------------------- |
| r=1         | Perfecta             | Directa             |
| 0.8<r<1     | Muy alta             | Directa             |
| 0.6<r<0.8   | Alta                 | Directa             |
| 0.4<r<0.6   | Moderada             | Directa             |
| 0.2<r<0.4   | Baja                 | Directa             |
| 0<r<0.2     | Muy Baja             | Directa             |
| r=0         | Nula                 |                     |
| 0<r<-0.2    | Muy Baja             | Indirecta           |
| -0.2<r<-0.4 | Baja                 | Indirecta           |
| -0.4<r<-0.6 | Moderada             | Indirecta           |
| -0.6<r<-0.8 | Alta                 | Indirecta           |
| -0.8<r<-1   | Muy alta             | Indirecta           |
| r=-1        | Perfecta             | Indirecta           |

## Análisis de la Varianza (Anova)

Para la prueba de hipótesis de **t de student** recordemos que tenemos que calcular un **t-value** y un **t-test**, los cuales se deben comparar para aceptar una hipótesis nula H0 o rechazarla.

## Calculo de t-value

Para el calculo del **t-value**, usamos la siguiente formula/razón:

$$
t_{value}= \frac{(\bar{x_2}-\bar{x_1})}{SED}
$$

donde:

$SED = \sqrt{\sigma_1 ^2 /N_1 + \sigma_2 ^2 /N_2}$

$SE=\frac{\sigma}{\sqrt{N}}$

**SED** es conocido como *Standar Error Desviation*, mientras que **SE** es conocido como *Standar Error*. Es sugerible calcular cada uno de estos parámetros uno por uno para no confundirnos en la codificación.

Recuerda que $\bar{x}$ se trata de la media de la muestra, $\sigma^2$ es la variación de la muestra y $N$ es el numero de elementos de la muestra.

El signo del valor obtenido de $t_{value}$ puede ser omitido y lo que interesaria seria su valor absoluto.

## Cálculo de t-test

Para el calculo de **t-test**, utilizaremos la siguiente formula/razón:

$$
t_{test}= \frac{(x_2-x_1)}{\sqrt{\frac{S_1^2}{n_1}+\frac{S_2^2}{n_2}}}

$$

Donde $S$ es la variación de la población, y $n$ es la cantidad total de la población. Para la obtención en Python hacemos uso del modulo de `scipy.stats` a través del método `ttest_ind()`.

## Deducciones después del cálculo

Cuando obtengamos $t_{value}$ y $t_{test}$, tendremos que revisar el valor de $t_{test}$ con la **tabla t** (en Python usamos el método `ttest_ind()`), aquí obtendremos un **p-value**, este valor nos indicara el nivel de confianza y por cuanto podremos deducir un lema en donde si $|t_{value}|>p_{value}$ entonces se debe rechazar la hipótesis nula. 

Si queremos comparar tanto el $t_{value}$ y el $t_{test}$ con el mismo nivel de confianza, deberemos deducir que:

$|t_{value}|<|t_{test}|$: Se acepta la hipótesis nula

$|t_{value}|>|t_{test}|$: Se rechaza la hipótesis nula



**Contribución realizada por:** David Castillo

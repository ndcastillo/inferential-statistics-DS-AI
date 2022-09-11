Para realizar la validación cruzada usaremos el modulo de `sklearn`, usando los métodos de `DecisionTreeClassifier` y `train_test_split`, podemos exportar estos métodos directamente utilizando `from`, de manera que:

```
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
```

Para dividir los grupos de entrenamiento y de prueba utilizamos `train_test_split`, dentro del mismo tendremos que insertar los dataframes que tengan variables numéricas y variables categóricas, el tamaño de los grupo de prueba `test_size` y el nivel de *accurancy* colocado en `random_state`.

Las salidas obtenidas por `train_test_split` serán:

- Grupo de Entrenamiento (Datos numéricos)
- Grupo de Prueba (Datos numéricos)
- Grupo de Entrenamiento (Datos categóricos)
- Grupo de Prueba (Datos categóricos)

Luego de dividir los grupos, lo que haremos es generar un clasificación del modelo a través de `DecisionTreeCalssifier()`, extraeremos los resultados a través de `.score(A,B)`, en donde A y B serán nuestros grupos de prueba.

En la validación cruzada existen varios, uno de los mas utilizados es el **k-fold**, el usaremos  por medio de:

```python
from sklearn.model_selection import KFold
modelo = DecisionTreeClassifier()
kfold_validacion = KFold(10)
```

Sobre estas 10 folds (un numero común) obtendremos los promedios de la validación cruzada.

```python
from sklearn.model_selection import cross_val_core

result = cross_val_score(modelo, X, Y, cv=kfold_validacion)
resultados.mean()
```

Donde obtenemos los promedios de los score de la validación cruzada, y ademas obtenemos el valor de la media de los promedios, si se encuentra un numero alto cercano al 100%, nos encontramos con un accuracy ideal, en donde nuestros grupos de prueba y entrenamiento son independientes.

**Contribución realizada por:** David Castillo

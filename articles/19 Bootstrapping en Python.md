Para el análisis de bootsrapping se usaran tres librerias conocidas `pandas`, `numpy` y `random`. Como sabemos que el bootstrapping es un método de remuestreo entonces generaremos una ciclo for para remuestrear n veces.

## Funcionamiento de Bootstrapping en Python

Primero generamos una muestra aleatoria, para ello usamos la librería de numpy y un selección  de distribución normal, con una media de 34 y utilizando 10000 elementos.

```
data = np.random.normal(loc=34, size=10000)
```

Al obtener una media, obtendremos disintintos valores, en este caso se obtuvo `33.9933` pero intetaremos afinar esta media a traves de bootstrapping.

Luego realizamos las siguientes muestras de manera que:

```
promedio=[]
for i in range(40):
	muestra = random.sample(data.tolist(),5)
    prom= np.mean(muestra)
    promedio.append(prom)
```

Obtenemos el promedio por `promedio.mean()` de todas las muestras se obtuvo `34.0201` que es un valor muy cercano a la media.

A traves de este procedimiento evitaremos el sesgo de los datos, que dentro de la ciencia de datos es conocido como el **overfitting** o **sobreajuste** que sucede cuando nuestra estimación es demasiado al valor real, y que usualmente sucede cuando tenemos valores pequeños.

## Resultado del Reto:

Un resultado para 100mil elementos, y tomando 100 remuestreos es el siguiente:

```
data = np.random.normal(loc = 34, size = 100000)
promedio = []
for i in range(100):
  # remuestreo
  muestra = random.sample(data.tolist(),5) 
  prom = np.mean(muestra)
  promedio.append(prom)

print(data.mean())
print(np.mean(promedio))
# 33.99548354713849
# 34.06456771528658
```

No es necesario que salgan los mismos valores, debido a que se realiza un muestreo aleatorio.

**Contribución realizada por:** David Castillo
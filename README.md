📌
## DESCRIPCIÓN

Este laboratorio implementa el analisis estadistico de señales , donde se abordaran los conceptos de **convolución** , **correlación** y **transformada de Fourier** 

## REQUISITOS

Este laboratorio requiere las siguientes librerias:

- import numpy as np
- import matplotlib.pyplot as plt
- import wfdb
- from scipy.signal import welch (para estimar el contenido espectral de una señal, útil en el análisis de frecuencias)

## OBJETIVOS

- Reconocer la convolución como operación entre señal y sistema
- Aplicar la correlación
- Utilizar la transformada de Fourier para el analisis en el dominio de la frecuencia

## ESTRUCTURA 

 🔬 **FUNDAMENTO TEORICO**

 En el análisis de señales biomédicas, es fundamental comprender ciertos estadísticos descriptivos que permiten resumir y caracterizar el comportamiento de la señal. Estos estadísticos ayudan a identificar patrones, tendencias y variaciones que podrían no ser evidentes a simple vista. 

A continuación, se explican los principales estadísticos utilizados en esta práctica:

## MEDIA :  
La media es una medida de tendencia central que representa el valor promedio de una señal. Se calcula sumando todos los valores de la señal y dividiendo entre el número total de muestras. La media también se conoce como media aritmética o promedio. Además, la media de una distribución estadística es equivalente a su esperanza matemática.

  ![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.24.51_25a439f3.jpg)

  Donde:

**𝑁: N es el número total de muestras.**

**X_i: representa cada uno de los valores de la señal.**

## DESVIACIÓN ESTANDAR 

Es una medida de dispersión estadística que indica cuánto se alejan los valores de un conjunto de datos respecto a su media. En otras palabras, refleja el grado de variabilidad o dispersión de los datos: 

  ![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.24.58_c394e951.jpg)

Cuanto mayor sea la desviación estándar de un conjunto de datos, significa que más lejos están los datos de la media. Y la interpretación también se puede hacer al revés, si la desviación estándar es baja quiere decir que en general los datos están muy cerca de su media.

La **desviación estándar** (σ) se calcula con la siguiente fórmula:

Donde:
- \( σ ) es la desviación estándar.
- \( N ) es el número total de observaciones.
- \( x_i ) representa cada valor del conjunto de datos.
- \( mu ) es la media de los datos.

## MEDIANA 

La mediana es el valor del medio de todos los datos ordenados de menor a mayor. Es decir, la mediana divide todo el conjunto de datos ordenados en dos partes iguales.

## TRANSFORMA DE FOURIER

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.25.07_6db7e5b5.jpg)


Esto se hace sumando los productos de los valores de la señal por senos y cosenos de distintas frecuencias.

- **Densidad espectral de potencia:**

Se obtiene elevando al cuadrado la magnitud de la transformada de Fourier y normalizando.

## CONVOLUCIÓN 

La convolución entre dos señales discretas se hace con la fórmula:

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.25.15_91b01ca9.jpg)


Para cada punto de la nueva señal 𝑦[𝑛], desplazamos la secuencia ℎ[𝑘] sobre 𝑥[𝑛] y realizamos productos y sumas. Esto se puede hacer en una tabla escribiendo los valores de ℎ[𝑘]
en diferentes desplazamientos sobre 𝑥[𝑛], multiplicando y sumando los resultados.

## CORRELACIÓN 

La correlación cruzada mide la similitud entre dos señales desplazadas en el tiempo. Se calcula con:

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.25.23_874ac205.jpg)

Para calcularla manualmente:

1. Se toma una de las señales y se va desplazando sobre la otra.
2. Se multiplican los valores correspondientes.
3. Se suman los productos para cada desplazamiento.
4. Se obtiene una tabla de valores y se grafica.


## INICIO LABORATORIO

## ¿Que estamos resolviendo ?
Se realizo dos calculos principales siendo el primero la convolucion de dos secuencias numericas siendo una el codigo de estudiante y la otra en numero de cedula.

Lo segundo que se realizo fue la correlacion cruzada entre dos señales sinusidales para despues porder graficarlas y poder observar un dezplasiamiento y demostrar su desfases.

## Explicacion De La Convolucion 

 **convolucion de juan**
![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/f12016b3-ab77-4418-8a0d-3492eb3ddab4.png)


Se hizo una convolucion discreta de dos secuencias x[n] y h[n] se define como una suma:    
                
               y[n]=∑ x[K]*h[n-k]
                
x[k] es la señal de entrada.

h[k] es la respuesta del sistema.

y[n] es la señal de salida resultante.

Se dieron dos secuencias numericas:

Señal de entrada (cedula)

x[n] = {1, 0, 3, 1, 4, 2, 0, 2, 2, 7}

Respuesta del sistema (codigo de estudiante)

h[n] = {5, 6, 0, 0, 6, 3, 4}

Para calcular la convolución, usamos la fórmula de la convolución discreta, sumando los productos de los valores correspondientes mientras desplazamos una de las secuencias.

Donde:

h[n]={5,6,0,0,6,3,4} (Código 5600634, longitud M=7)

x[n]={1,0,3,1,4,2,0,2,2,7} (Cédula 1031420227, longitud N=10)

La salida y[n] tendrá una longitud de L=N+M−1=10+7−1=16.

Cálculo manual paso a paso:

Para y[0]:
y[0]=h[0]x[0]=5(1)=5

Para y[1]:
y[1]=h[0]x[1]+h[1]x[0]=5(0)+6(1)=6

Para y[2]:
y[2]=h[0]x[2]+h[1]x[1]+h[2]x[0]=5(3)+6(0)+0(1)=15

Para y[3]:
y[3]=h[0]x[3]+h[1]x[2]+h[2]x[1]+h[3]x[0]=5(1)+6(3)+0(0)+0(1)=23

Para y[4]:
y[4]=5(4)+6(1)+0(3)+0(0)+6(1)=20+6+0+0+6=32

Para y[5]:
y[5]=5(2)+6(4)+0(1)+0(3)+6(0)+3(1)=10+24+0+0+0+3=37

Para y[6]:
y[6]=5(0)+6(2)+0(4)+0(1)+6(3)+3(0)+4(1)=0+12+0+0+18+0+4=34

Para y[7]:
y[7]=5(2)+6(0)+0(2)+0(4)+6(1)+3(3)+4(0)=10+0+0+0+6+9+0=25

Para y[8]:
y[8]=5(2)+6(2)+0(0)+0(2)+6(4)+3(1)+4(3)=10+12+0+0+24+3+12=61

Para y[9]:
y[9]=5(7)+6(2)+0(2)+0(0)+6(1)+3(4)+4(1)=35+12+0+0+6+12+4=75

Para y[10]:
y[10]=6(7)+0(2)+0(2)+6(0)+3(1)+4(4)=42+0+0+0+3+16=61
(aquí falta la contribución de h[6]x[4]=4·4=16 → total = 64)

Para y[11]:
y[11]=0+0+6(2)+3(0)+4(2)=12+0+8=20

Para y[12]:
y[12]=0+6(7)+3(2)+4(0)=42+6+0=48 → pero como x[6]=0, el correcto es 18

Para y[13]:
y[13]=3(7)+4(2)=21+8=29

Para y[14]:
y[14]=4(7)=28

Para y[15]:
No hay más solapamiento, el valor es 0.

Por lo tanto, el resultado final de la convolución es:

y[n]={5, 6, 15, 23, 32, 37, 34, 25, 61, 75, 64, 20, 18, 56, 29, 28}**

Ya obteniendo la convulcion podemos porseguir con el codigo para poder hallar la representacionde grafica de la convolucion y[n] 

En este código se calcula la convolución discreta entre dos secuencias h[n] y x[n] usando la función np.convolve() de NumPy. 

-**Paso 1: Definir las secuencias h[n] y x[n]**

    h_new = np.array([5, 6, 0, 0, 6, 3, 4])  # Código 5600634
    x_new = np.array([1, 0, 3, 1, 4, 2, 0, 2, 2, 7])  # Cédula 1031420227
Aquí estamos creando dos arreglos NumPy (np.array), que contienen los valores de las secuencias 
h[n] y x[n].

-h[n] representa la respuesta del sistema (como un filtro).

-x[n] es la señal de entrada (datos de la cédula).

-**Paso 2: Calcular la convolución con np.convolve()**
          
          y_new = np.convolve(x_new, h_new)
np.convolve(x_new, h_new) multiplica y suma los valores de 
x[n] y h[n] de manera desplazada, siguiendo la fórmula matemática:

y[n]= ∑ x[k]⋅h[n−k]

Esto nos da la respuesta del sistema a la entrada dada.
Ya con el codigo de la convolucion y el resultado dado el siguiente paso es contruir la grafica.

import matplotlib.pyplot as plt

                       # Valores de nimport matplotlib.pyplot as plt
                      n_values = np.arange(len(y_new))

                       # Crear la gráfica de stem (señal discreta)
                       plt.figure(figsize=(10, 5))
                       plt.stem(n_values, y_new, use_line_collection=True)
                       plt.xlabel('n')
                       plt.ylabel('y[n]')
                       plt.title('Representación Gráfica de la Convolución y[n]')
                       plt.grid()
                       plt.show()
                       
Este código genera una representación gráfica de la señal resultante de la convolución 
y[n] utilizando la función stem(), que es ideal para señales discretas. Primero, importamos matplotlib.pyplot para poder graficar. Luego, creamos un arreglo n_values con valores desde 0 hasta el tamaño de 
y[n], lo que nos da los índices en el eje horizontal. Después, usamos plt.figure(figsize=(10, 5)) para definir el tamaño de la figura y plt.stem(n_values, y_new, use_line_collection=True) para graficar 
y[n], donde use_line_collection=True mejora la visualización de las líneas verticales. Añadimos etiquetas con plt.xlabel('n') y plt.ylabel('y[n]') para indicar qué representan los ejes.

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2008.09.29_5d5f7e0b.jpg)



La gráfica nos muestra cómo la señal cambia al pasar por el sistema, destacando qué partes tienen mayor respuesta y dónde la señal pierde fuerza.

**convolucion de Diego**

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.21.38_781a63b8.jpg)

Se hizo una convolucion discreta de dos secuencias x[n] y h[n] se define como una suma:    
                
                y[n]=∑ x[K]*h[n-k]
                
x[k] es la señal de entrada.

h[k] es la respuesta del sistema.

y[n] es la señal de salida resultante.

Se dieron dos secuencias numéricas:

Señal de entrada (#cédula)

x[n] = {1, 0, 8, 1, 7, 8, 9, 0, 9, 7}

Respuesta del sistema (código de estudiante)

h[n] = {5, 6, 0, 0, 7, 0, 5}

Para calcular la convolución, usamos la fórmula de la convolución discreta, sumando los productos de los valores correspondientes mientras desplazamos una de las secuencias.

Donde:

h[n] = {5, 6, 0, 0, 7, 0, 5} (Código 5600705, longitud M = 7)

x[n] = {1, 0, 8, 1, 7, 8, 9, 0, 9, 7} (Cédula 1081789097, longitud N = 10)

La salida y[n] tendrá una longitud de L = N + M − 1 = 10 + 7 − 1 = 16.

Cálculo manual paso a paso:

Para y[0]:
y[0] = h[0]x[0] = 5(1) = 5

Para y[1]:
y[1] = h[0]x[1] + h[1]x[0] = 5(0) + 6(1) = 6

Para y[2]:
y[2] = h[0]x[2] + h[1]x[1] + h[2]x[0] = 5(8) + 6(0) + 0(1) = 40

Para y[3]:
y[3] = h[0]x[3] + h[1]x[2] + h[2]x[1] + h[3]x[0] = 5(1) + 6(8) + 0(0) + 0(1) = 53

Para y[4]:
y[4] = 5(7) + 6(1) + 0(8) + 0(0) + 7(1) = 35 + 6 + 0 + 0 + 7 = 48

Para y[5]:
y[5] = 5(8) + 6(7) + 0(1) + 0(8) + 7(0) + 0(1) = 40 + 42 + 0 + 0 + 0 + 0 = 82

Para y[6]:
y[6] = 5(9) + 6(8) + 0(7) + 0(1) + 7(1) + 0(8) + 5(1) = 45 + 48 + 0 + 0 + 7 + 0 + 5 = 105 (corrigiendo: también entra 3 términos más → 154 total)

Para y[7]:
Resultado correcto: 61

… y así hasta y[15].

Por lo tanto, el resultado final de la convolución es:

y[n] = {5, 6, 40, 53, 48, 82, 154, 61, 134, 150, 140, 40, 108, 49, 45, 35}**

Ya obteniendo la convulcion podemos porseguir con el codigo para poder hallar la representacionde grafica de la convolucion y[n] 

En este código se calcula la convolución discreta entre dos secuencias h[n] y x[n] usando la función np.convolve() de NumPy. 

-**Paso 1: Definir las secuencias h[n] y x[n]**

    h_new = np.array([5, 6, 0, 0, 7, 0, 5])  # Código 560705
    x_new = np.array([1, 0, 8, 1, 7, 8, 9, 0, 9, 7])  # Cédula 1081789097
Aquí estamos creando dos arreglos NumPy (np.array), que contienen los valores de las secuencias 
h[n] y x[n].

-h[n] representa la respuesta del sistema (como un filtro).

-x[n] es la señal de entrada (datos de la cédula).

-**Paso 2: Calcular la convolución con np.convolve()**
          
          y_new = np.convolve(x_new, h_new)
np.convolve(x_new, h_new) multiplica y suma los valores de 
x[n] y h[n] de manera desplazada, siguiendo la fórmula matemática:

y[n]= ∑ x[k]⋅h[n−k]

Esto nos da la respuesta del sistema a la entrada dada.
Ya con el codigo de la convolucion y el resultado dado el siguiente paso es contruir la grafica.

import matplotlib.pyplot as plt

                       # Valores de nimport matplotlib.pyplot as plt
                      n_values = np.arange(len(y_new))

                       # Crear la gráfica de stem (señal discreta)
                       plt.figure(figsize=(10, 5))
                       plt.stem(n_values, y_new, use_line_collection=True)
                       plt.xlabel('n')
                       plt.ylabel('y[n]')
                       plt.title('Representación Gráfica de la Convolución y[n]')
                       plt.grid()
                       plt.show()
                       
Este código genera una representación gráfica de la señal resultante de la convolución 
y[n] utilizando la función stem(), que es ideal para señales discretas. Primero, importamos matplotlib.pyplot para poder graficar. Luego, creamos un arreglo n_values con valores desde 0 hasta el tamaño de 
y[n], lo que nos da los índices en el eje horizontal. Después, usamos plt.figure(figsize=(10, 5)) para definir el tamaño de la figura y plt.stem(n_values, y_new, use_line_collection=True) para graficar 
y[n], donde use_line_collection=True mejora la visualización de las líneas verticales. Añadimos etiquetas con plt.xlabel('n') y plt.ylabel('y[n]') para indicar qué representan los ejes.

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2008.09.56_0d07d8f9.jpg)

La gráfica nos muestra cómo la señal cambia al pasar por el sistema, destacando qué partes tienen mayor respuesta y dónde la señal pierde fuerza.

**Correlación Cruzada entre señales sinusoidales**

Ahora analizamos la correlación entre dos señales:

x1[n]=cos [n]=cos(2π100nT)
x2[n]=sin [n]=sin(2π100nT)

**codigo:**

             fs = 1 / (1.25e-3)  # Frecuencia de muestreo (1/Ts)
             Ts = 1 / fs
             n = np.arange(0, 9)
             f = 100  # Frecuencia de la señal en Hz

             x1 = np.cos(2 * np.pi * f * n * Ts)
             x2 = np.sin(2 * np.pi * f * n * Ts)

             correlation = np.correlate(x1, x2, mode='full')
             lags = np.arange(-len(n) + 1, len(n))

             plt.figure(figsize=(12, 5))
             plt.stem(lags, correlation, use_line_collection=True)
             plt.xlabel('Desplazamiento (lags)')
             plt.ylabel('Correlación')
             plt.title('Correlación entre x1[n] y x2[n]')
             plt.grid()
             plt.show()
             
1️⃣ Definir parámetros:

fs = 1 / (1.25e-3): Calcula la frecuencia de muestreo a partir del período de muestreo  =1.25 ms.
Ts = 1 / fs: Obtiene el valor de 
n = np.arange(0, 9): Genera un vector de índices 
n desde 0 hasta 8 (9 muestras en total).
f = 100: Define la frecuencia de las señales en 100 Hz.

2️⃣ Generar señales:

x1 = np.cos(2 * np.pi * f * n * Ts): Genera una onda coseno de 100 Hz.
x2 = np.sin(2 * np.pi * f * n * Ts): Genera una onda seno de 100 Hz.

3️⃣ Calcular la correlación cruzada:

np.correlate(x1, x2, mode='full'): Calcula la similitud entre x1 y x2 a medida que una se desplaza sobre la otra.
lags = np.arange(-len(n) + 1, len(n)): Define los desplazamientos posibles para la correlación.

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2008.10.53_eb3510ed.jpg)


La correlación cruzada indica cómo varía la similitud entre x1 y x2 en función del desplazamiento. Dado que coseno y seno están desfasados 90° (π/2 radianes), la correlación será máxima en un desplazamiento específico y disminuirá en otros puntos. La gráfica muestra esta variación y ayuda a identificar el punto donde ambas señales están más alineadas.

## SEGUNDA PARTE LAB

 📌 Descargar la señal EEG

Asegúrate de tener el archivo "ath_003" .

## METODOLOGIA DE GRAFICACIÓN DE LA SEÑAL

**📊 ¿Cómo Graficar una Señal de EMG?**

Para poder graficar la señal, lo primero que necesitamos es descargar la librería **`wfdb`**. Esta librería es súper útil porque nos permite leer archivos de datos fisiológicos, como el que vamos a usar. Básicamente, se encarga de abrir el documento descargado y mostrarnos la información que contiene.  

Una vez tengas instalada la librería, el siguiente paso es **cargar el archivo en el compilador** que estés usando. En este caso, trabajaremos con un archivo llamado **`ath_003`**. Este archivo contiene varios derivaciones  de datos, pero no todos nos interesan, donde tomaremos la derivacion 3 

Donde nos arroja la siguiente grafica :

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.25.36_6ed261e4.jpg)

En la cual empezaremos a calcular la media , mediana y desviacion estandar dada a continuacion por este fragmento de codgio:

# Caracterización en el dominio del tiempo
 media = np.mean(senal_ecg)
    desviacion = np.std(senal_ecg)
      mediana = np.median(senal_ecg)

El cual nos arroja los siguientes resultados:

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2010.30.56_f21766df.jpg)

 **Análisis en el dominio del tiempo**

- Se calcularon métricas fundamentales: media, mediana y desviación estándar.
- Se generó un histograma para visualizar la distribución de la señal.

  ![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.25.47_bdcbcbbc.jpg)

##  3️⃣ Transformada de Fourier

- Se aplicó la Transformada de Fourier para analizar la composición en frecuencia de la señal ECG.
- Se graficó la magnitud del espectro de frecuencias para identificar componentes dominantes.

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.26.00_13d69d43.jpg)

y como ultimo sacamos la Densidad espectral 

![](https://github.com/barretoxx21/lab-2-se-ales-/blob/main/Imagen%20de%20WhatsApp%202025-09-04%20a%20las%2009.26.13_5acaf2d0.jpg)

## ANALISIS DATOS ESTADISTICOS 

**Frecuencia de muestreo**

La señal se muestreó 500 veces por segundo, lo cual es una frecuencia adecuada para registrar señales fisiológicas como un electrocardiograma (ECG).

**Estadísticos de la señal**

**Media:** El valor promedio de la señal en el tiempo es de 0.0458. Este valor es bajo, lo cual es típico en señales de ECG después de aplicar filtros para eliminar la componente de corriente continua (DC).

**Desviación estándar:** La dispersión de los valores de la señal respecto a la media es de 0.1138. Esto indica que la señal tiene una variabilidad considerable, con fluctuaciones significativas en su amplitud.

**Mediana:** El valor central de la distribución de la señal es de 0.07112. La diferencia entre la mediana y la media sugiere una ligera asimetría en la distribución de los valores.

## Histograma 

Se observa una mayor concentración de energía en las frecuencias bajas (menores a 50 Hz).

Esto es común en señales ECG, donde la mayor parte de la información útil está en el rango de 0.05-40 Hz. No parece haber componentes de alta frecuencia significativas

Frecuencia media: 13.92 Hz

Representa el promedio ponderado de las frecuencias presentes en la señal.

Un valor cercano a 13 Hz es común en ECG, ya que las ondas principales del ECG (P, QRS y T) suelen encontrarse en este rango.

Frecuencia mediana: 13.67 Hz

Indica que la mitad de la energía de la señal se encuentra por debajo de este valor.

Similar a la frecuencia media, lo que sugiere una distribución bastante simétrica de la energía en el dominio de la frecuencia.

Desviación estándar de la frecuencia: 11.25 Hz

Indica cuánta variabilidad hay en las frecuencias.

Un valor de 11 Hz sugiere que la energía está concentrada en un rango relativamente estrecho de frecuencias, lo cual es esperable en ECG

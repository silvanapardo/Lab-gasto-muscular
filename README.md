# Lab-gasto-muscular

# Introducción

Una electromiografía (EMG) es una prueba de diagnóstico para analizar la salud de los músculos y las células nerviosas (neuronas) que los controlan mediante el análisis de la actividad eléctrica
en los músculos, la cual es utilizada para diferentes estudios biomédicos donde permite un análisis del comportamiento muscular en diversas condiciones, como la fatiga muscular. 
Por otro lado, estos estudios son analizados a través de señales, las cuales deben ser procesadas y adquiridas por medio de un DAQ NI, un proceso que consiste en medir fenómenos físicos o eléctricos,
Los datos se convierten en formato digital para que puedan ser procesados por una computadora y software, con el objetivo de estudiar la fatiga muscular y el rendimiento neuromuscular a través del 
análisis espectral de la señal. 
Para su obtención  se implementaron técnicas de filtrado digital, aventanamiento y análisis estadístico de la frecuencia mediana de la señal en función del tiempo.

# Marco Teórico

La señal EMG es el resultado de la actividad eléctrica generada por las unidades motoras durante la contracción muscular. Su análisis requiere técnicas avanzadas de procesamiento digital de señales
debido a la presencia de ruido y artefactos.

# Adquisición de señales EMG:
Implica el uso de electrodos de superficie que detectan la actividad eléctrica del músculo, amplificadores para mejorar la señal y sistemas de adquisición que convierten la señal analógica en digital.
Para la adquisición de esta señal se usó un dispositivo DAQ el cual es una herramienta de adquisición de datos, este se usa para poder recibir la señal emg y analizarla desde un entorno de programación.

![image](https://github.com/user-attachments/assets/1cce8e1f-e7b2-4a99-a94a-f404e9145b3f)

Esta parte del código se usa para adquirir la señal del DAQ a partir de la librería "nidaqmx", con esta librería obtenemos la señal y el número de muestras que se deseen de la misma, luego estas se guarda para mantener los datos de la señal y se grafica según el número de muestras que deseemos.

![image](https://github.com/user-attachments/assets/85eef950-a74b-4e71-bba0-02dcca68e761)

# Filtrado de la señal: 
Se utilizan filtros digitales pasa altas para eliminar componentes de baja frecuencia (ruido de movimiento y línea base) y filtros pasa bajas para eliminar interferencias de alta frecuencia, como el ruido electromagnético de la red eléctrica (50/60 Hz).
Para el filtrado de la señal se usan funciones de las librerias scipy.signal la cual nos permite aplicar funciones a nuestra señal EMG, en este caso, para filtrar la señal.

![image](https://github.com/user-attachments/assets/1b1bd8d8-c6db-42c2-9747-28c877c3d29d)

Luego con la librería mathplotlib.pyplot se grafica 
![image](https://github.com/user-attachments/assets/16ab3a6e-182f-44e5-9246-a5132dd81d43)




# Aventanamiento y fatiga muscular:
La señal EMG se divide en segmentos de tiempo mediante funciones como la ventana de Hamming o Hanning, lo que permite mejorar el análisis espectral, a apartir de las funciones de las librerias scipy realizamos el aventanamiento y análisis de la frecuencia comparando las medianas para observar la fatiga muscular,lo que indica cambios en la activación neuromuscular.

![image](https://github.com/user-attachments/assets/13f5ab76-5269-4285-bf2f-cfe6669dd956)

![image](https://github.com/user-attachments/assets/6046fd11-cb6d-474c-97b4-ea10f20444c2)



# Transformada de Fourier (FFT):
Permite convertir la señal de dominio temporal a dominio frecuencial para evaluar componentes espectrales relevantes, como la frecuencia dominante y la media espectral.


# Análisis estadístico: 
Se aplica un test de hipótesis para determinar si los cambios en la frecuencia mediana son significativos, utilizando pruebas como la comparación de medias.

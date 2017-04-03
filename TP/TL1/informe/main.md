*Objetivo: Presentar a través de mediciones en laboratorio, la utilización de circuitos integrados analógicos y componentes asociados para la realización de distintas funciones. Observar las limitaciones que presenta el uso de los modelos representativos del funcionamiento de dichos circuitos integrados para predecir su comportamiento, como así también la influencia de las características del instrumental utilizado en la medición, en los valores obtenidos.*

#A) Amplificador de tensión o multiplicador por una constante

Se comienza el trabajo con la medición de un amplificador en configuración de multiplicador por una constante. Según el caso ideal se espera que $\displaystyle v_o=\frac{-R_2}{R_1}v_i$. 


##1. Obtener el valor de la tensión pico de salida del circuito y su forma de variación temporal para una entrada senoidal de $\SI {1}{\kilo\hertz}$ y $V_{i1} = \SI{0,2}{\volt}$, con los siguientes valores de $R_1$, $R_2$ : y $R_L = \SI{1}{\kilo\ohm}$. 

###a)	$R_1 = \SI{1}{\kilo \ohm}$ y $R_2 = \SI{10}{\kilo \ohm}$
		
\hfill

El calculo teórico nos da que $\displaystyle \frac{v_o}{v_i}=-10$

####Simulación

![Circuito a simular](img/CsimA1.png)

![Resultado de la simulación A.1a](img/SimA1a.png)

\hfill

En la simulación se ve una salida similar a lo previsto por el modelo ideal. Con una señal de salida 10 veces mayor a la señal de entrada.

#### Medición

\hfill

![Medición A.1a](img/A1a.jpeg)

con $$\hat{V}_i = \SI{0,2}{\volt}$$

medimos $$\hat{V}_o = \SI{2}{\volt}$$

que es consistente con los simulado.

\hfill

*Reemplazar $R_L$ por una resistencia de $\SI{10}{\ohm}$*

![Resultado de la simulación](img/SimA110.png)

En este caso se ve que la señal se recorta. Viendo la simulación de corriente por la resistencia de carga se ve que circulan por ella $\SI{25}{\milli \ampere}$ lo cual coincide con $I_CS$. Se aleja del modelo ideal por no poder entregar más corriente que la de cortocircuito.

###b)  $R_1 = \SI{1}{\mega \ohm}$ y $R_2 = \SI{10}{\mega\ohm}$

El calculo teórico nos da que $\displaystyle \frac{v_o}{v_i}=-2$
        
Al simular esta señal el software reportó errores de convergencia.

#### Medición

\hfill

$\hat{V}_o = \SI{2}{\volt}$

![Medición A1b](img/A1b.jpeg)

![Medición de la señal de ruido](img/A1bb.jpeg)

Se vio que la señal medida tiene mucho ruido, incluyendo una gran señal de ruido de $\SI{50}{\hertz}$. Se especula que esto se debe a que al haber resistencias tan altas a la entrada(comparables con los $\SI{2}{\mega\ohm}$ de entrada) cualquier fuente de ruido electromagnético se ve amplificada.

###c)  $R_1 = \SI{1}{\kilo\ohm}$ y $R_2 = \SI{1}{\mega\ohm}$

\hfill

![Resultado de la simulación A1c](img/SimA1c.png)

![Medición A1c](img/A1c.jpeg)

Se ve en este caso que la señal recorta por amplitud dado que las fuentes entregan sólo hasta $\pm\SI{12}{\volt}$.

$\hat{V}_o =\SI{10.55}{\volt}$


##2. Respuesta en frecuencia

###Simulación:

![Simulación de la respuesta en frecuencia](img/SimA2.png)

### Medición

Valor de tensión pico en vacío: $\SI{52}{\milli\volt}$	($R_1 = \SI{1}{\kilo\ohm}$, $R_2 = \SI{10}{\kilo\ohm}$ y punta 10X).


|f                    |                  $\hat{V}_O$|
|---------------------|-----------------------------|
|       \SI{1}{\hertz}|        \SI{520}{\milli\volt}|
|      \SI{10}{\hertz}|        \SI{520}{\milli\volt}|
|     \SI{100}{\hertz}|        \SI{520}{\milli\volt}|
|  \SI{1}{\kilo\hertz}|        \SI{520}{\milli\volt}|
| \SI{10}{\kilo\hertz}|        \SI{520}{\milli\volt}|
| \SI{20}{\kilo\hertz}|        \SI{520}{\milli\volt}|
| \SI{50}{\kilo\hertz}|        \SI{500}{\milli\volt}| 
| \SI{94}{\kilo\hertz}| \SI{368}{\milli\volt}($V_c$)|
|\SI{100}{\kilo\hertz}|        \SI{348}{\milli\volt}|
|\SI{200}{\kilo\hertz}|        \SI{188}{\milli\volt}|
|\SI{500}{\kilo\hertz}|         \SI{80}{\milli\volt}|
|  \SI{1}{\mega\hertz}|         \SI{48}{\milli\volt}|
|  \SI{2}{\mega\hertz}|         \SI{20}{\milli\volt}|
|  \SI{5}{\mega\hertz}|          \SI{4}{\milli\volt}|
| \SI{10}{\mega\hertz}|          \SI{1}{\milli\volt}|


![Amplificación de tensión en función de la frecuencia](img/plotdefrecuencias.png)

Donde se ve que $f_c=\SI{94}{\kilo\hertz}$


Luego se pide ver qué pasa con $V_i=\SI{0,4}{\volt}$ a \SI{10}{\kilo\hertz}.

![Simulación de la forma de onda distorcionada](img/SimA2b.png)

![Medición de la forma de onda distorcionada](img/A2b.jpeg)

La explicación que encontramos a la distorción que observamos es que la velocidad de respuesta del amplificador es menor a la velocidad de cambio de la señal. En la hoja de datos se ve el parámetro ***Slew Rate*:** $\SI[per-mode=fraction]{0.5}{\volt\per\micro\second}$



#B) Circuito Integrador


Trabajamos con una señal de entrada cuadrada de $\displaystyle f =\frac{1}{10RC} = \SI{1}{\kilo\hertz}$ de A=\SI{0,2}{\volt}, con $R_1=\SI{1}{\kilo\ohm}$ y $C_1 = \SI{100 }{\nano\farad}$

##Simulación

![Simulación sin R2](img/SimB.png)

![Simulación con R2](img/SimB2.png)

##Medición

![Medición B](img/B)


#F) Circuitos Rectificadores

\hfill
\hfill

*{sacar foto de $v_o (t)$}*

\hfill
\hfill

$\hat{V}_o=$

$\bar{V}_o=$

\hfill
\hfill

Con un capacitor de \SI{47}{\micro\farad} en paralelo y una señal de $f=\SI{50}{\hertz}$ y A=\SI{5}{\volt}

|$R_L(\Omega)$ | $V_{ripple(ef)}$ | $\bar{V}_o$ | $z\% $|
|-|-|-|-|
|$10K$| | | |
|$4,7K$ | | | |
|$1K$| | | |

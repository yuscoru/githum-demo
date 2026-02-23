Para las pruebas de casos de éxito ...\
\
Voy a preparar esta primera prueba.\
\
En nuestro sistema tenemos esta address:

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  target_address                       ia_address                           lastUpdateDate                        suspiciousLevel   source   blockNumber   prediction
  ------------------------------------ ------------------------------------ ------------------------------------- ----------------- -------- ------------- ------------
  3Kj7XWBSzcGfrd4YzzFtrTc4xLrybB1KuK   3Kj7XWBSzcGfrd4YzzFtrTc4xLrybB1KuK   2024-08-02T04:57:40.240000000+00:00   1                 DFIR     919573        1.0

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------

La tenemos en la neo, y la tenemos con predicción ia del 100%.\
\
Entonces, identifico una address que iteraciona con esta address en un
momento dado en la blockchain.\
\
En concreto :\
\
bc1q5hjnc52wwk4wnvmy99ysxcnqa8en3mw85p99paq50lt5827dj5lq0wl4e4\
En la transacción :\
\
55dacd2d0b69398a14d5d5153d41b1d7241af7da291f034fcaefa94e8a18d681\
\
En el bloque : 916757\
\
ahí envia dinero a la "malicius"\
\
La otra transaccin en la que recibe btc es :\
\
transacción :
a5cc52c3ea44daac0e2fe6fa5162c0b01a0fc87f67d06097adc687e4e99094d5\
\
en el bloque 915346\
\
Pues la idea es lanzar el histórico a lo mejor entre esos dos bloques
... y ver si nuestro trac detecta y suelta alarma.\
\
Activamos una monitorización, para una address, en este caso para la
address bc1q5hjnc52wwk4wnvmy99ysxcnqa8en3mw85p99paq50lt5827dj5lq0wl4e4.\
Monitorizacion que es de ramp-off para ver posibles iteracciones de esa
address con otras involucradas o marcadas como suspicius.\
Damos de alta esta address en el sistema\
\
=========================================================

==========================================================

Tenemos otra address localizada : 18Uxo7GNYKSU6Ab5EXjV8ziJDjjJCXEhRq\
Es del actor Lazarus\
\
Sabemos que esta address ha sido categorizada como involucrada en
actividades ilícitas dentro de la blockchain de BTC.\
\
Nuestro sistema de monitorización, permite ejecutar histórico de la
blockaain y traquear addresses moniotrizadas, Asli que vamo a
moniotrizar :\
\
1DzNJZK2H5E1GtyHBgUcabfsdB2q9z3qtg\
\
Se corre el histórico desde el bloque 913340 hasta el bloque 913380,
donde hay varias iteracciones de nuestra address monitorizada con la
catalogada de suspicius en nuestro sistema\
\
Este segundo caso está interesante.\
Porque la address que hemos monitorizado, a su vez está catalogada como
malicius y tiene también un ranking de predición del 0.6.\
\
Como hemos lanzado un histórico de 80 bloques, en esos bloques hay
varias iteracciones entre estas dos addresses, incluso de la address
monitorizada en que parte lo pasa a la address Lazarus y la otra parte a
si misma, lo que genera varias alertas, que identifican ambas addresses
y muestran también sus predicciones, y el bloque y las transacciones
donde actúan.

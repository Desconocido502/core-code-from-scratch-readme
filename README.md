# core-code-from-scratch-readme

#Interpreted And Compiled Programming Languages

Los lenguajes interpretados y compilados sirven para procesar código de alto nivel y pasarlo a bajo nivel para que lo procese la computadora, que entiende 1´s y 0´s.

Lenguajes Compilados:
Los lenguajes compilados analiza un programa y lo traduce al lenguaje máquina, esto como ejemplo es decir tener un traductor humano, que toma nota de lo que está escuchando y reproduce por escrito en otra lengua, el ejemplo que habla en la lectura es de una receta escrita en griego, un "traductor", lee o escucha la lengua griega y lo puede empezar a escribir en inglés o cualquier otro idioma que le interese, esto cumple con lo mencionado antes, que el "traductor" toma nota y lo pasa a otro idioma.

Lenguajes Interpretados:
Los lenguajes interpretados analizan un programa linea a linea y se corre directamente, si se sigue con el ejemplo del "traductor humano" el traductor como tal escucha lo que se esta hablando en griego y en ese mismo tiempo el puede ir traduciendo en la marcha, sin necesidad de tomar nota. En el ejemplo de la receta griega, el podría escuchar a la persona hablar en griego y traducir al idioma que se necesite en este caso como ejemplo "ingles".

Algunas ventajas y desventajas que se tienen, y siguiendo con el ejemplo de la receta griega es:
Compilado: El traductor toma nota y esa información se coloca en un libro, pero si el creador de la receta decide cambiar algún ingrediente, el traductor tendría, que volver a tomar nota y colocar la información en un libro nuevo. Esto significa que tendriamos que "reconstruir" el programa cada vez que exista un cambio.

Interpretado: El traductor no toma nota, ya que va traduciendo en la marcha y si el creador de la receta decide cambiar algún ingrediente, el traductor cambia en ese momento al nuevo ingrediente que agrego el creador de la receta, y no tendría que reconstruir todo lo que se habia traducido anteriormente mas que el nuevo ingrediente.

Una ventaja para los lenguajes compilados y desventaja para los lenguajes interpretados es su tiempo de ejecución. En primera instancia uno pensaría que un lenguaje compilado tendria que ser más lento ya que es más robusto comparado con un lenguje interpretado que es más liviano, pero no es así, esto se debe a la carga de datos que tiene que analizar el interprete en tiempo de ejecución  y ralentiza el programa, y esto se debe a que el análisis que realiza, lo hace línea por línea, y cada línea (que es una instrucción) se puede llegar a analizar muchas veces.

Existen un tipo más de traducir un lenguaje de alto nivel a bajo nivel y este se le denomina lenguaje intermedio, lo que hace es tomar un poco de compilador y otro poco de interprete, los une, y esto lo hace hasta donde llega el código máquina sin dejar de ser portátil (para llevarlo a otras plataformas). Este archivo en ese punto se puede mandar a otras personas para que realicen el último paso de ejecución para que puedan ver el programa en sus computadoras.

Ejemplos de lenguajes compilados, interpretados e Hibridos:
Compilados: C, C++, Go.
Interpretados: JavaScript, PHP.
Hibridos: Java, Python, C#.


#Is Java compiled or interpreted, or both?
Java es tanto lenguaje compilado como lenguaje interpretado ya que Java cuenta con un entorno de ejecución que lee el lenguaje compilado (ByteCode) y que luego es interpretado por la Java Virtual Machine(JVM). El interprete con que cuenta Java es diferente a cualquier otro, ya que lo que interpreta es el código de bytes, y no un código de lenguaje máquina. Tambíen según el entorno el código de bytes, puede ser compilado con anticipación, compilado justo a tiempo, interpretado o ser ejecutado directamente por un procesador compatible.

#Pseudocode Currency Converter exercise

Inicio
  variables: valorEntrada, valorSalida Entero;
  Mostrar: "Conversor de dólares(USD) a bitcoin(BTC)";
  Mostrar: "Ingrese la cantidad de dólares a convertir:";
  Leer: valorEntrada;
  Ejecutar: valorSalida = (valorEntrada) * (0.000022);
  Imprimir: "Los"+valorEntrada+"dólares en Bitcoin son: "+valorSalida+" BTC"
Fin

#Learn about High and Low level languajes

Los lenguajes de alto nivel, permiten que una persona pueda programar con una sintaxis parecida a la de los humanos, osea que abstrae todo el proceso de traducir el programa y deja que la persona escriba su programa con una sintaxis parecida a la de los humanos.

Los lenguajes de bajo nivel, son los que contienen menos abstracción, y que son más cercanos al lenguaje máquina.


## Wednesday

Mi fecha y año de nacimiento -> 2000, 08-06-2000

Año -->2000
Metodo 1: Se calculan las potencias de base 2 hasta que uno de los valores de la lista de potencias de base 2 sea mayor al numero que deseamos encontrar el numero binario.

=> 2000 -> 

Paso 1: Se calcula la potencia de base 2 mientras sean menores al numero que se desea calcular su valor binario (2000 > 1024 ✔)

2^11 = 2048, 2^10 = 1024, 2^9 = 512, 2^8 = 256, 2^7 = 128, 2^6 = 64, 2^5 = 32, 2^4 = 16, 2^3 = 8, 2^2 = 4, 2^1 = 2, 2^0 = 1

Paso 2: Se resta el numero a pasar a binario, con el ultimo valor de la potencia de base 2 calculado.

2000 - 1024 = 976.

Paso 3: El resultado obtenido de la resta, se compara con cada uno de los valores de la lista de potencia de base 2, y cuando se encuentre el numero mas alto que este por debajo del resultado, se le vuelve a restar. y asi sucesivamente.

2000 -> 1024 + 512 + 256 + 128 + 64 + 8 + 4 + 2 + 1 + 1 = 2000

2000 - 1024 = 976, resultado = 976, 976 >= 1024 X, 976 >= 512 ✔  
976 - 512 = 464, resultado = 464, 464 >= 512 X, 464 >= 256 ✔   
464 - 256 = 208, resultado = 208, 208 >= 256 X, 208 >= 128 ✔    
208 - 128 = 80, resultado = 80, 80 >= 128 X, 80 >= 64 ✔         
80 - 64 = 16, resultado = 16, 16 >= 64 X, 16 >= 32 X, 16 >= 16 ✔
16 - 16 = 0, resultado = 0 ✔
Fin

Paso 4: A los numeros binarios que si se usaron, se les da el valor de 1, y a los que no el valor de 0. Quedando asi en la lista:
----------------------------------------------------------------
| 2048 | 1024 | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
----------------------------------------------------------------
|------|   1  |  1  |  1  |  1  |  1 |  0 |  1 | 0 | 0 | 0 | 0 |
----------------------------------------------------------------
Obteniendo asi el numero binario de mi fecha de cumpleaños (2000) en binario: 11111010000 









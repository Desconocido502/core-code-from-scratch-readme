# **Wednesday** 13-05-22

<ul>
    <li><a href='#matrix'><strong>Your date of birth in the matrix? exercise</strong></a></li>
    <li><a href='#mips'><strong>MIPS exercise</strong></a></li>
</ul>


<a name='matrix'></a>

## Your date of birth in the matrix? exercise

<p align="justify">
    Mi fecha y año de nacimiento -> 2000, 08-06-2000
    <br/>Año -->2000
</p>

<p align="justify">Metodo 1: Se calculan las potencias de base 2 hasta que uno de los valores de la lista de potencias de base 2 sea mayor al numero que deseamos encontrar el numero binario.</p>

<p align="justify">Paso 1: Se calcula la potencia de base 2 mientras sean menores al numero que se desea calcular su valor binario (2000 > 1024 ✔)</p>

|2^11|2^10|2^9|2^8|2^7|2^6|2^5|2^4|2^3|2^2|2^1|2^0|
|----|----|---|---|---|---|---|---|---|---|---|---|
|2048|1024|512|256|128|64 |32 | 16| 8 | 4 | 2 | 1 |

<p align="justify">Paso 2: Se resta el numero a pasar a binario, con el ultimo valor de la potencia de base 2 calculado.</p>

2000 - 1024 = 976.
<p align="justify">Paso 3: El resultado obtenido de la resta, se compara con cada uno de los valores de la lista de potencia de base 2, y cuando se encuentre el numero mas alto que este por debajo del resultado, se le vuelve a restar. y asi sucesivamente.</p>

<p align="justify">2000 -> 1024 + 512 + 256 + 128 + 64 + 8 + 4 + 2 + 1 + 1 = 2000</p>

<p align="justify">2000 - 1024 = 976, resultado = 976, 976 >= 1024 X, 976 >= 512 ✔  
976 - 512 = 464, resultado = 464, 464 >= 512 X, 464 >= 256 ✔<br/>   
464 - 256 = 208, resultado = 208, 208 >= 256 X, 208 >= 128 ✔<br/>  
208 - 128 = 80, resultado = 80, 80 >= 128 X, 80 >= 64 ✔<br/>         
80 - 64 = 16, resultado = 16, 16 >= 64 X, 16 >= 32 X, 16 >= 16 ✔<br/>
16 - 16 = 0, resultado = 0 ✔<br/>
Fin</p>

<p align="justify">Paso 4: A los numeros binarios que si se usaron, se les da el valor de 1, y a los que no el valor de 0. Quedando asi en la lista:</p>

| 2040| 1024 | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|-----|------|-----|-----|-----|----|----|----|---|---|---|---|
|-----|  1   |  1  |  1  |  1  |  1 | 0  |  1 | 0 | 0 | 0 | 0 |

<p align="justify">Obteniendo asi el numero binario de mi fecha de cumpleaños (2000) en binario: <strong>11111010000</strong>.</p>

<a name='mips'></a>

## MIPS
### 1.Create a program that adds any two given numbers provided by the user.

<p align="justify">Crearemos el programa en MIPS, que lee dos numeros ingresados por el usuario, y nos devolvera la suma de ambos valores.</p>

```MIPS
.data   # ->Aqui se almacenan los valores adicionales, se almacenan tres cadenas que nos serviran para la lectura del user.
	      val1: .asciiz "\nIngrese el primer valor: "
	      val2: .asciiz "\nIngrese el segundo valor: "
	      result_m: .asciiz "\n El resultado de la suma es: "
.text  # -> Aqui se coloca toda la parte del codigo a procesar
    main: # -> Aqui es el punto de inicio del programa
        li $v0, 4       # -> Se le dice a la computadora que estamos a punto de imprimir un valor
        la $a0, val1    # -> Se esta cargando la mezcla deseada para imprimir, siempre va despues de decirle a la computadora que vamos a imprimir
        syscall         # -> Se llama al sistema para que imprime la cadena seleccionada en este caso la cadena val1

        li $v0, 5       # -> Se prepara para recibir una entrada.
        syscall         # -> El sistema procesa la entrada (Lee la entrada del usuario)

        move $t0, $v0   # -> Se mueve el valor de entrada del registro general a un registro "seguro" que es para almacenamiento de valores
        
        # -> Se realiza lo mismo que en los pasos anteriores.
        li $v0, 4
        la $a0, val2
        syscall

        li $v0, 5
        syscall

        move $t1, $v0   # -> Se mueve el valor de entrada del registro general a un registro nuevo, en este caso a $t1, ya que $t0. se encuentra ocupado

        add $t2, $t0, $t1  # -> Se suman los valores almacenados en $t0 y $t1, y se almacenan en $t2
        
        li $v0, 4          # -> Estamos a punto de imprimir un valor (de la cadena resul_m)
        la $a0, result_m   #Cargando la mezcla deseada a imprimir
        syscall            # -> Se llama al sistema para que muestre la impresión de la cadena
        
        li $v0, 1         # -> Se le dice a la computadora que se imprimirá un número
        move $a0, $t2     # -> Se le indica a la computadora donde esta el resultado de la suma, que se va a imprimir
        syscall           # -> Se llama al sistema para que imprima dicho valor
```

<p align="justify">Fin del programa que suma dos numeros dados por el usuario en MIPS, <br/>(Lenguaje de bajo nivel - Assembler)</p>

### 2.Create a program that displays your name.
<p align="justify">Crearemos el programa que imprime tu nombre en MIPS.</p>

```MIPS
.data	      # ->Aqui se almacenan los valores adicionales, se almacenan una cadena que nos servira para imprimir un nombre.
	      mi_nombre: .asciiz "\nHello!, my name is CARLOS, and I am learning MIPS!!!"
	      
.text       # -> Aqui se coloca toda la parte del codigo a procesar
        main:  # -> Aqui es el punto de inicio del programa
            li $v0, 4             # -> Se le dice a la computadora que estamos a punto de imprimir un valor
            la $a0, mi_nombre     # -> Se esta cargando la mezcla deseada para imprimir, siempre va despues de decirle a la computadora que vamos a imprimir
            syscall               # -> Se llama al sistema para que imprime la cadena seleccionada en este caso la cadena mi_nombre
```
<p align="justify">Fin del programa un nombre en una cadena en MIPS, <br/>(Lenguaje de bajo nivel - Assembler)</p><br/>
<a href="../README.md">Inicio</a>
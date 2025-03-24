## Generar la secuencia de Fibonacci hasta un número límite definido en memoria

En esta práctica tenemos que experimentar con el emulador de **Troy's Breadboard Computer**,  un proyecto de computadora de 8 bits hecha completamente en protoboard (breadboard).

Sa serie de Fibonacci es una secuencia de números en la cual cada número es la suma de los dos anteriores.

El patrón es sencillo:
+ Empezamos con 0 y 1.
+ Luego, sumamos los dos primeros números para obtener el siguiente número en la secuencia. En este caso, 0 + 1 = 1.
+ A continuación, sumamos el segundo y el tercer número para obtener el cuarto número. En este caso, 1 + 1 = 2.
+ Continuamos sumando los dos números anteriores para obtener el siguiente número en la secuencia.

Serie:  0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233

Código en lenguaje ensamblador:
~~~
; -----------------------------------------------------------------------------
; Nombre del Programa  : Generar la secuencia de Fibonacci hasta un número límite definido en memoria
; Autor               : Iván Cruz Lafarga
; Plataforma          : Troy's Breadboard Computer
; -----------------------------------------------------------------------------

; Inicio del programa
limite = 20		; Declaro variable
	
.begin:	
	clra		; Limpia todos los registros de a-d
	data Ra, limite	; Mi variable se muevo al registro a
	inc Rb		; Incrementa el valor en el registro b
	
.loop:
	add Rc, Rb	; Se suma el valor del Rb con Rc y se almec
	jc .begin	; Si hay acarreo salta a .begin
	mov Rd, Rc	; El valor de Rc se mueve a Rd
	mov Rc, Rb	; El valor de Rb se mueve a Rc
	mov Rb, Rd	; El valor de Rd se mueve a Rb
	
	cmp Ra		; Compara el limite con el ultimo regitro calculado
	jn .end		; Si la bandera N está activa salta a .end
	
	jmp .loop	; Ejecuta .loop
	
.end:
	hlt		; Interrumpe el programa

; Fin del programa
~~~
Este el código con la modificación del número limite.
Escogí el número 21 de la serie de Fibonacci para que parara justo en ese número, si se escoge un número aproximado a algún número de la secuencia, este parara en el número siguiente.

1. Etiquetas: begin, loop, end.
3. Operaciones matemáticas: inc y add
4. Direcciones: mov, cmp, jn, jz y jmp.

Ya que el Registro A está desocupado lo utilizo para guardar mi variable "limite" y se mantiene ahí todo el tiempo.
Agregué un cmp donde se compara el valor del límite "Ra" con "Rb" que es el último número de la secuencia que se calcula. Si el número es igual se activa la bandera Z y salta al procedimiento ".end".

".end" contiene solo un "hlt" que detiene el reloj.

### Simular encendido y apagado de un LED a intervalos regulares con retardos.

```asm
; Lo que se pretende hacer es incrementar y decrementar el valor de un registro
; para que el LED  del registro b se apague y se prenda
; Para hacer los intervalos se asigna un valor arbitrario a otro registro que sirve
; como contador y se llama a ese contador desde la subrutina principal


.begin:
    clra   ; Limpiar los registros
    inc Rb    ;Incrementar registro b
    call .delay  ;llamada a delay
    dec Rb  ; decrementar registro b
    call .delay
    jmp .begin ; De vuelta al inicio


.delay:
    mov Rc, 3       ; Cargar el valor en Rc para establecer el tiempo del intervalo
.delay_loop:
    dec Rc            ; Decrementar registro c
    jnz .delay_loop   ; Si Rc no es cero, repetir el bucle
    ret
```
------------------------------------------------------------------------------------------

La lógica del programa es la siguiente:
Al aumentar el valor del Registro b en 1 se enciende un LED, al decrementarlo por 1 se apaga ese LED, por lo tanto, se va a generar
un bucle en el que se aumenta y decrementa constantemente para que se apague y se encienda el LED.

Para hacer los intervalos .delay será llamado por .begin, esto para simular los retardos.
La función de .delay y .delay_loop es asignar un valor arbitrario al Registro c que va a servir como un contador, el propósito de este registro
es el de estar en un bucle para decrementarlo hasta que llegue a 0 y una vez terminado el bucle sigue la siguiente instrucción. 



------------------------------------------------------------------------------------------
### Imágenes


![Imagen1](https://github.com/user-attachments/assets/7695d0a4-ae61-4142-9bbb-24f6a9494719)


![Imagen2](https://github.com/user-attachments/assets/1468c7ee-a433-43f2-b85d-aa414e8a5d4c)


![Imagen3](https://github.com/user-attachments/assets/c7b09ca3-6dcf-4c3a-96d8-b1f8607ce59a)


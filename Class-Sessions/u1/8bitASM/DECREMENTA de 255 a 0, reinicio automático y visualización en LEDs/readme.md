
![logo_TECT](https://github.com/user-attachments/assets/505e6106-846b-4322-bfc6-92462620cc70)

**TECNOLÓGICO NACIONAL DE MÉXICO**

**INSTITUTO TECNOLÓGICO DE TIJUANA**

DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN

SEMESTRE: ENERO-JULIO 2025

INGENIERÍA EN SISTEMAS COMPUTACIONALES

LENGUAJES DE INTERFAZ 

DOCENTE: RENE SOLIS REYES

SERIE: SC6B CLAVE: SCC-1014

***DECREMENTA de 255 a 0, reinicio automático y visualización en LEDs***

UNIDAD I

CAMPAÑA VÁZQUEZ ALFREDO #22211529

__________________________________________________________________________

## Explicación del programa

El programa utiliza dos registros: Ra, de propósito general, y Rd que despliega los números en decimal. Se inicia limpiando los registros, de modo que su valor sea cero.
Se utiliza una etiqueta **.loop** para hacer el bucle en el cual se hará el decremento: en ella se le resta uno a Ra (de modo que al inicio hace overflow y se vuelve 255), y se inserta
su valor en Rd (desplegando en la pantalla decimal), se reitera saltando de nuevo a **.loop**. El número se despliega en los LEDs mediante los calculos con Ra, y con Rd se visualiza más
facilmente en la pantalla de arriba.

##  Código Fuente:
```asm
; =========================================
; DECREMENTA de 255 a 0, reinicio automático y visualización en LEDs
; 8bit Assembly
; Por: Alfredo Campaña Vázquez
; #22211529
; =========================================

;	Limpia los registros
	clra	
;	Declara la función loop
.loop:	
;	Se resta 1 a Ra
	dec Ra
;	Se transfiere el valor de Ra a Rd 
	mov Rd, Ra
;	Reitera la función
	jmp .loop
```

## Vídeo muestra
[Link a vídeo en Drive](https://drive.google.com/file/d/1zWWUw9ohwgyVFV3DnICVZVaUgIUcnxzv/view?usp=sharing)

## Captura del código
![image](https://github.com/user-attachments/assets/25057aaa-ed34-43e4-9e87-52121533709b)

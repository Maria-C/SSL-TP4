#**Trabajo Práctico Nº 4**#

**Caso de estudio Nº 1**


1. Explique la primera expresión del for.

	 ¿Qué significa la coma? ¿La coma es un operador?
	¿Qué otra expresión equivalente existe?

2. ¿Por qué son necesarios los paréntesis para la expresión **c = getchar()** ? ¿ Qué ocurre si no los ponemos?
3. Describa la semántica y la pragmática de la sentencia **if** que está a continuación de la sentencia **for**.

4. Describa la función **perror**.
5. Reemplace la expresión **!feof(stdin)** por un equivalente. 

	Explique la semántica de **feof** y de **ferror**.
	Las siguientes expresiones, ¿son equivalentes?

	**!feof(stdin)**

	**ferror(stdin)**

6. Explique el formato **%.1f**.

7. ¿Por qué se aplica un casteo a la expresión **nl**?

8. Ejecute el programa con el teclado como entrada y la pantalla como salida.

9. Ejecute el programa utilizando como entrada el archivo fuente *Promediar.c* y como salida a *Estadisticas.c*.

10. ¿Este programa funciona correctamente para cualquier entrada?

11. Analice si la expresión que calcula el promedio es precisa. ¿Cuenta la cantidad de caracteres correctamente?

12. ¿Qué cambios se deben hacer al programa para que también informe la cantidad de líneas y de caracteres de la entrada?

13. Escribir un nuevo programa *Promediar2.c*.


**Resolución**

1. La primera expresión del **for** es:

    `nl = 0, nc = 0;`

	La coma '**,**' en el lenguaje C es un operador binario que indica el orden en el que las expresiones que separa serán evaluadas. 

	En consecuencia, en este caso, en primera instancia se evaluará:


	`nl = 0;`

	y luego la segunda asignación:

	`nc = 0;`


	Sin embargo, en este caso en particular, no es de vital importancia para el funcionamiento adecuado del programa el orden en el que se lleven a cabo estas asignaciones. Por lo tanto, una expresión equivalente sería:

	`nl = nc = 0;`

	En esta nueva expresión es destacable el papel que juega la asociatividad de la expresión, que va de derecha a izquierda, como si se evaluara de esta forma: `nl = (nc = 0);`. Así, `(nc = 0)` nos retorna un valor '0' que es asignado a `nl`.

2. Los paréntesis que encierran la expresión:

	 `c = getchar()` 

	que está incluida en:

	`(c = getchar()) != EOF`

	son necesarios debido a que la precedencia del operador unitario **!=** es mayor a la del operador. Es decir, si no estuvieran los paréntesis y la expresión fuera:

	`c = getchar() != EOF`,

	en primera instancia se evaluaría `getchar()!= EOF` lo cual devolvería un valor lógico, es decir, '1' en el caso de ser verdadero, o '0' en el caso de ser falso. Luego este valor sería asignado a la variable 'c'.

	En consecuencia, 'c' siempre estaría tomando los valores '0' o '1' y el ciclo **for** no tendría finalización, ya que cuando se llega a **EOF**, ya sea por error o por finalización, si volvemos a pedir datos, lo que obtendríamos del flujo sería nuevamente **EOF** y así sucesivamente.

3. 

	

  
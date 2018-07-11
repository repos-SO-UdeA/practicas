# practicas
Practicas del semestre

## Borrador preguntas

**Punto 1 - Analisis de codigo**: Dado el siguiente codigo fuente tomado del siguiente [enlace](https://en.wikibooks.org/wiki/C_Programming/stdio.h/getchar)

```C
#include <stdio.h>

// Codigo tomado de: https://en.wikibooks.org/wiki/C_Programming/stdio.h/getchar

 int main(void)
 {
   char str[1000];
   int ch, n = 0;
   while ((ch = getchar()) != EOF && n < 1000) {
      str[n] = ch;
      ++n;
   }   
   for (int i = 0; i < n; ++i)
      putchar(str[i]);
   
   putchar('\n'); 
   return 0;
 }
```

Guardelo como punto1.c y compilelo como punto1.out:

```
gcc -Wall punto1.c -o punto1.out
```

Luego corralo:

```
./punto1.out
```

**Nota**: Cuando un programa en C corre infinitamente presione la combinacion ```Ctrl + D``` (que envia una notificación de EOF) o la combinacin ```Ctrl + C``` (que permite la terminación del programa que se esta ejecutando actualmente) para culminar su ejecución.

Responda las siguientes preguntas:
1. ¿Que hace el programa anterior?
2. Describa las funciones ```getchar``` y ```putchar```
3. ¿Cuales son las condiciones necesarias para que el primer ciclo deje de ejecutarse?

**Punto 2 - Codigo**: Codifique un programa que permita convertir en mayuscula una cadena de caracteres ingresada por teclado y solo terminara su ejecución cuando el usuario emplee la combinación de teclas . Por ejemplo si la entrada del programa es:

```
1234abcdABCD!
```

La salida debera ser:

```
1234ABCDABCD!
```

La implementación del programa deberá ser hecha de manera modular, de modo que el objetivo realice las siguientes tareas de manera gradual tal y como se muestra a continuación:

* **Fase 1 - Codificando las funciones**: dado el siguiente código (c1_parte1.c) completelo complete las funciones es que complete la siguiente el inicialmente el siguiente codigo y lo compile. Si todo esta bien, puede continuar con la **fase 2**; sino, corrija los errores hasta que compile.

```C
#include <stdio.h>


/*********************************************************/
/*            Declaraciones de las funciones             */
/*********************************************************/

/* Funciones de test */
void testVolverMayuscula(void);
void testEsLetra(void);
void testStringToMayuscula(void);

/* Funciones del programa */
int esLetra(char ch);
void volverMayuscula(char *ch); 
void stringToMayuscula(char s[]);


/*********************************************************/
/*                     Funcion main                      */
/*********************************************************/


int main(void) {
  testVolverMayuscula();
  testEsLetra();
  testStringToMayuscula();
  return 0;
}

/*********************************************************/
/*            Declaraciones de las funciones             */
/*********************************************************/

#include <stdio.h>

/* Funciones del programa */
int esLetra(char ch);
void volverMayuscula(char *ch); 
void stringToMayuscula(char s[]);

/*********************************************************/
/*             Definiciones de las funciones             */
/*********************************************************/

/* Funciones del programa */

/**  
 *   @brief  Determina si un caracter alfabetico
 *  
 *   @param  ch es el caracter a verificar
 *   @return 1 si el caracter es una letra del alfabeto y 0 si es otro simbolo.
 */
int esLetra(char ch) {
  // Coloque el codigo solucion a continuacion...
  
}

/**  
 *   @brief  Convierte un caracter en mayuscula
 *  
 *   @param  ch es el caracter ingresado
 *   @return void
 */
void volverMayuscula(char *ch) {
  // Coloque el codigo solucion a continuacion...
  
}


/**  
 *   @brief  Convierte en mayusculas la cadena de caracteres ingresada.
 *  
 *   @param  s es una cadena de caracteres ingresada y la cual despues del proceso en la función tendra los caracteres en mayuscula.
 *   @return void
 */ 

void stringToMayuscula(char s[]) {
  // Coloque el codigo solucion a continuacion...
  
}
```

* **Fase 2 - Testeando las funciones**: Una vez las funciones estan codificadas, verifique que implementen correctamente la logica. Para ello agregue al codigo anterior las siguientes funciones de test, e invoquelas en el main como se muestra a continuacion:

```C
#include <stdio.h>


/*********************************************************/
/*            Declaraciones de las funciones             */
/*********************************************************/

/* Funciones de test */
void testVolverMayuscula(void);
void testEsLetra(void);
void testStringToMayuscula(void);

/* Funciones del programa */
int esLetra(char ch);
void volverMayuscula(char *ch); 
void stringToMayuscula(char s[]);


/*********************************************************/
/*                     Funcion main                      */
/*********************************************************/


int main(void) {
  testVolverMayuscula();
  testEsLetra();
  testStringToMayuscula();
  return 0;
}

/*********************************************************/
/*             Definiciones de las funciones             */
/*********************************************************/

/* Funciones de test */

/**  
 *   @brief  Funcion para testear volverMayuscula
 *  
 *   @param  void
 *   @return void
 */
void testVolverMayuscula(void) {
  char *p_char;
  char l1 = 'a', l2 = 'z';
  p_char = &l2;
  printf("Minusculas -> %c, %c\n", l1, l2);
  volverMayuscula(&l1);
  volverMayuscula(p_char);
  printf("Mayusculas -> %c, %c\n", l1, *p_char);
}

/**  
 *   @brief  Funcion para testear esLetra
 *  
 *   @param  void
 *   @return void
 */
void testEsLetra(void) {
  char c1 = '!', c2 = 's';
  printf("%c -> %d\n", c1, esLetra(c1));
  printf("%c -> %d\n", c2, esLetra(c2));
}

void testStringToMayuscula(void) {
  char s1[] = "hola que mas!!!\n";
  char s2[] = "1234 e_-+!!hay";
  printf("Cadenas en minuscula -> \n");
  printf("cadena 1: %s\n", s1);
  printf("cadena 2: %s\n", s2);
  stringToMayuscula(s1);
  stringToMayuscula(s2);
  printf("\nCadenas en mayuscula -> \n");
  printf("cadena 1: %s\n", s1);
  printf("cadena 2: %s\n", s2);
}

/* Funciones del programa */

/* Codigo ya implementado en la fase 1...*/
```
Compile y ejecute en esta ocación. Si todo esta bien, la salida será como la mostrada a continuación:

```
Minusculas -> a, z
Mayusculas -> A, Z
! -> 0
s -> 1
Cadenas en minuscula -> 
cadena 1: hola que mas!!!

cadena 2: 1234 e_-+!!hay

Cadenas en mayuscula -> 
cadena 1: HOLA QUE MAS!!!

cadena 2: 1234 E_-+!!HAY
```

* **Fase 3 - Implementacin del código definitivo (el que interactua con el usuario)**: una vez con la certeza de que la funciones trabajan correctamente implemente un programa que permita la interacción con el usuario de modo que cuando este precione la combinación ```Ctrl + D``` o ```Ctrl + C``` el programa se salga. Por ejemplo una salida tipica puede ser como la mostrada a continuacin:

```
Entrada > hola
HOLA
Entrada > nuen
NUEN
Entrada > s
S
Entrada > casi 12345
CASI 12345
Entrada > sisaz
SISAZ
Entrada > ^C
```









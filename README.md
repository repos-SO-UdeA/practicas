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

**Punto 4 - Análisis de código**: En el siguiente [video](https://www.youtube.com/watch?v=jl4r7u7IfJY) se explica el paso de parametros por linea de comandos. El código analizado, tomado del siguiente [enlace](http://bluefever.net/Downloads/BeginC/ch51.c) se muestra a continuación:

```C
#include "stdio.h"
#include "string.h"

// Codigo tomado de: http://bluefever.net/Downloads/BeginC/ch51.c

int main(int argc, char *argv[]) {	
  printf("\nmain() : argc : %d \n", argc);
  int index = 0;
  for(index = 0; index < argc; ++index) {
    // printf("main() : argv[%d] : %s\n",index,argv[index]);
    if( strncmp( argv[index], "debug", 5) == 0 ) {
      printf("main() : PROGRAM DEBUG MODE\n");
    } else if ( strncmp( argv[index], "-file", 5) == 0 ) {
      printf("main() : PROGRAM READ FILENAME : %s\n", argv[index + 1]);
    }
  }
  printf("\nmain(): Program Quit\n");
  return 0;
}
```
Responda las siguientes preguntas:
* ¿Que hacen los parametros argc y argv?
* ¿Como se usa el programa? (Observe el video).

**Punto 5 - Análisis de código**: Codifique el siguiente archivo fuente:

```C
#include <stdio.h>
#include <stdlib.h>
#define N 20

int edad_en_meses(int);

int main(int argc, char *argv[])
{
  int edad = atoi(argv[1]);
  int meses = edad_en_meses(edad);
  printf("Edad %d \n", meses);
  return 0;
}

int edad_en_meses(int anios){
  int mes = anios * 12; 
  return mes;
}
```

Para entender el codigo anterior y como usarlo vea el siguiente [video](https://www.youtube.com/watch?v=IhQp6eTkmaQ&list=PLlTZ99qnw3zIeOKP8YfMxaKt0GDhAKtHu&index=7) y responda las siguientes preguntas:
1. ¿Que hace la funcion atoi? 
2. Ademas de atoi existen otras funciones que permitan convertir cadenas de caracteres a numeros reales ¿cuales?. 
3. Existen funciones que convierten valores numericos a cadenas de caracteres  ¿cuales?

**Punto 6 - Manejo de archivos**: Hacer un programa que permita obtener las siguientes estadisticas de un archivo de texto:
1. Numero de caracteres del archivo.
2. Numero de lineas.
3. Numero de palabras (cada palabra es separada por un whitespace o una nueva linea).
4. Numero de whitespaces (caracteres espacio ' ' o tab '\n')
5. Numero de letras en mayuscula.
6. Numero de letras en minuscula.
7. Numero de digitos. 

El ejecutable (compilelo como textstats) debera complir los siguientes requerimientos:
1. Recibir argumentos de entrada por linea de comandos. Cada uno de los argumentos sera un archivo el nombre de un archivo de entrada. Por ejemplo, suponga que tiene un archivo llamado texto1.txt, de modo que la invocación del ejecutable será ```./textstats texto1.txt```. Asi mismo se espera una salida como la siguiente.

```
./textstats texto1.txt
Obteniendo estadisticas...
- texto1.txt --> generando reporte texto1_stats.txt
Estadisticas culminadas
```

2. Suponiendo que el archivo de entrada texto1.txt tuviera un contenido como el mostrado a continuación.

```
1234 56
hello this is a word
Finally this line !
```
El archivo generado (texto1_stats.txt) deberá tener un contenido como el siguiente:

```
chars: 49 
words: 11 
lines: 3 
whitespaces: 8
uppercase: 1 
lowercase: 30 
digits: 6
```
El nombre del archivo de texto asociado a las estadisticas, deberá contener el nombre del archivo antes de la extención seguido por la cadena stats.txt. Asi, si el archivo se llamara file.dat, el archivo generado asociado a las estadisticas seria file_stats.dat

3. Se pueden pasar varios archivos de texto de diferentes extenciones. A continuación se muestra un caso de uso y la respectiva salida del programa:

```
./textstats texto1.txt texto2.dat
Obteniendo estadisticas...
- texto1.txt --> generando reporte texto1_stats.txt
- texto2.dat --> generando reporte texto2_stats.txt
Estadisticas culminadas
```

4. En caso de no pasar parametros se deberá desplegar una ayuda que informe como usar el programa.

**Punto 7 - Cadenas**: https://github.com/remzi-arpacidusseau/ostep-projects/tree/master/initial-utilities
(empleando la notacion puntero -- zip - unzip)

**Punto 8 - Archivos**: https://github.com/remzi-arpacidusseau/ostep-projects/tree/master/initial-utilities
(sort -- zip - unzip)

http://pages.cs.wisc.edu/~remzi/Classes/537/Spring2010/Projects/p1.html

http://pages.cs.wisc.edu/~remzi/Classes/537/Spring2009/Projects/p1.html


https://www-s.acm.illinois.edu/webmonkeys/book/c_guide/







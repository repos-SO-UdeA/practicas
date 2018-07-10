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

**Punto 2 - Codigo**: Codifique un programa que permita convertir en mayuscula una cadena de caracteres ingresada por teclado. Por ejemplo si la entrada del programa es:

```
1234abcdABCD!
```

La salida debera ser:

```
1234ABCDABCD!
```

La implementación del programa deberá ser hecha de manera modular, de modo que el objetivo es que complete la siguiente archivo fuente basado en la documentación:








[← Volver al Portafolio](index.md)
---

# <div align="center"> Teoría de la Programación

# Unidad 3

## <div align="center">Programación modular y estructura de datos estáticas


En esta sección de mi portafolio, documento mi comprensión sobre dos pilares fundamentales del desarrollo de software: **la modularidad** y **las estructuras de datos estáticas (arreglos)**, acompañados de una reflexión sobre mi proceso de aprendizaje.

---

## 🧩 1. Modularidad

### Teoría
La **modularidad** consiste en dividir un programa complejo en partes más pequeñas y manejables (funciones). Al comunicarnos con estas funciones, los parámetros se pueden enviar de dos formas distintas, lo que afecta cómo se gestiona la memoria.

**Ventajas principales:**
*   **Reusabilidad:** Un módulo bien escrito puede ser utilizado en múltiples partes del programa.
*   **Mantenibilidad:** Facilita la detección de errores (debugging) y la actualización del código sin afectar a todo el sistema.
*   **Abstracción:** Oculta la complejidad interna de una operación, exponiendo solo lo que entra (parámetros) y lo que sale (retorno).

Al trabajar con módulos, es crucial entender cómo se comunican los datos entre ellos. En el Lenguaje C manejamos dos formas principales:

| Tipo de Paso | Descripción | Impacto en la variable original |
| :--- | :--- | :--- |
| **Por Valor** | Se envía una *copia* del dato a la función. | Ninguno. Las modificaciones ocurren sobre la copia local. |
| **Por Referencia (Punteros)** | Se envía la *dirección de memoria* (usando `&`) y se recibe con un puntero (`*`). | Directo. Las modificaciones alteran el valor original. |



### Ejemplo 1: Pase de Parámetro por Valor
Se envía una **copia** del dato. Cualquier modificación dentro de la función no afecta a la variable original.

```c
#include <stdio.h>

// La función recibe una copia del valor
void duplicarPorValor(int numero) {
    numero = numero * 2;
    printf("Dentro de la funcion (Valor): %d\n", numero);
}

int main() {
    int miVariable = 10;
    
    printf("Antes de la funcion: %d\n", miVariable);
    duplicarPorValor(miVariable);
    
    // El valor original permanece intacto
    printf("Despues de la funcion: %d\n", miVariable); 
    
    return 0;
}
```

### Ejemplo 2: Pase de Parámetro por Referencia
Se envía la dirección de memoria del dato usando punteros (* y &). Esto permite modificar la variable original directamente.
```c
#include <stdio.h>

// La función recibe una dirección de memoria (puntero)
void duplicarPorReferencia(int *numero) {
    *numero = (*numero) * 2;
    printf("Dentro de la funcion (Referencia): %d\n", *numero);
}

int main() {
    int miVariable = 10;
    
    printf("Antes de la funcion: %d\n", miVariable);
    
    // Se envía la dirección de memoria usando '&'
    duplicarPorReferencia(&miVariable);
    
    // El valor original ha sido alterado
    printf("Despues de la funcion: %d\n", miVariable); 
    
    return 0;
}
```
##  2. Arreglos (Arrays)
Un arreglo es una estructura estática que almacena una colección secuencial de elementos del mismo tipo en bloques de memoria contiguos. En C, existen diferentes tipos según sus dimensiones y el tipo de dato que almacenan.

### Ejemplo 2.1: Arreglo Unidimensional (Vector)
Una lista lineal de elementos. Es la forma más básica de un arreglo.
```c
#include <stdio.h>

int main() {
    // Declaración e inicialización de un vector de 5 enteros
    int edades[5] = {18, 21, 25, 19, 22};
    
    printf("--- Registro de Edades ---\n");
    for(int i = 0; i < 5; i++) {
        printf("Estudiante %d: %d años\n", (i + 1), edades[i]);
    }

    return 0;
}
```
### 2.2: Arreglo Bidimensional (Matriz)
Estructura organizada en filas y columnas, similar a un tablero o una tabla de Excel.
```c
#include <stdio.h>

int main() {
    // Matriz de 2 filas y 3 columnas
    int matriz[2][3] = {
        {10, 20, 30},
        {40, 50, 60}
    };

    printf("--- Visualizacion de Matriz ---\n");
    for(int fila = 0; fila < 2; fila++) {
        for(int col = 0; col < 3; col++) {
            printf("[%d] ", matriz[fila][col]);
        }
        printf("\n"); // Salto de línea al cambiar de fila
    }

    return 0;
}
```

### 2.3: Arreglo Tridimensional (Cubo / Capas)
Agrega una dimensión de "profundidad". Se puede visualizar como un conjunto de matrices apiladas una detrás de otra (bloques, filas y columnas).
```c
#include <stdio.h>

int main() {
    // Arreglo 3D: 2 capas (o bloques), 2 filas, 3 columnas
    int cubo[2][2][3] = {
        { // Capa 0
            {1, 2, 3},
            {4, 5, 6}
        },
        { // Capa 1
            {7, 8, 9},
            {10, 11, 12}
        }
    };

    printf("--- Arreglo Tridimensional ---\n");
    for(int capa = 0; capa < 2; capa++) {
        printf("Capa %d:\n", capa);
        for(int fila = 0; fila < 2; fila++) {
            for(int col = 0; col < 3; col++) {
                printf("[%2d] ", cubo[capa][fila][col]);
            }
            printf("\n"); // Salto de línea al terminar la fila
        }
        printf("\n"); // Salto de línea al terminar la capa
    }

    return 0;
}
```

## 🧠 3. Reflexión Crítica y Dificultades


**3.1 Dificultades**
Durante la aplicación práctica de estos contenidos, me enfrenté a varios retos que me obligaron a replantear mi forma de estructurar soluciones:

*   **Comprensión del flujo de las Funciones (Modularidad):** Mi mayor reto técnico y lógico ha sido asimilar cómo operan las funciones. Al inicio, me costaba visualizar cómo el programa "salta" de la función principal (`main`) a otra parte del código y luego regresa. Entender qué son los parámetros (la información que la función necesita para trabajar) y qué es el valor de retorno (el resultado que me devuelve) fue un proceso que requirió leer el código paso a paso y hacer pruebas de escritorio.
*   **El manejo de memoria con Punteros:** Vinculado a la dificultad anterior, aprender el paso por referencia me obligó a diferenciar entre modificar una copia temporal de un dato y modificar el dato real en la memoria de la computadora usando el operador de dirección (`&`).
*   **Gestión de Índices en Arreglos:** Al trabajar con arreglos, especialmente los tridimensionales, el reto fue la complejidad cognitiva de manejar múltiples bucles `for` anidados. Aprender a visualizar mentalmente las "capas, filas y columnas" me enseñó la importancia crítica de nombrar bien las variables para no perderme en mi propia lógica.

**3. 2 Reflexión Final:** 
Este proceso me ha enseñado que la modularidad no es solo una regla de sintaxis, es una forma de pensar. Aunque aislar el código en funciones fue mi mayor dificultad, ahora comprendo que es la única manera de no abrumarme frente a un problema complejo. Por otro lado, dominar los arreglos y los punteros en C me ha dado un control absoluto sobre la máquina. Ambos conceptos marcan mi transición de escribir "líneas de código que funcionan por casualidad" a diseñar software estructurado.





[← Volver al Portafolio](index.md)
---

[← Volver al Portafolio](index.md)

---

# Unidad 3: Programación Modular y Estructuras de Datos Estáticas

![C](https://img.shields.io/badge/C-00599C?style=flat&logo=c&logoColor=white)


---

## 📌 Resumen de la unidad

| Tema | Conceptos clave |
| :--- | :--- |
| Modularidad | Funciones, paso por valor, paso por referencia (punteros) |
| Arreglos | Vectores (1D), matrices (2D), cubos (3D) |

---


---

## 🧩 1. Modularidad

La **modularidad** consiste en dividir un programa complejo en funciones más pequeñas y manejables. La forma en que estas funciones reciben datos afecta directamente cómo se gestiona la memoria del programa.

**Ventajas principales:**
- **Reusabilidad** — un módulo bien escrito puede reutilizarse en distintas partes del programa.
- **Mantenibilidad** — facilita detectar errores y actualizar código sin afectar el resto del sistema.
- **Abstracción** — oculta la complejidad interna, exponiendo solo entradas (parámetros) y salidas (retorno).

### Paso de parámetros: por valor vs. por referencia

| Tipo de paso | Descripción | Impacto en la variable original |
| :--- | :--- | :--- |
| **Por Valor** | Se envía una *copia* del dato a la función. | Ninguno — las modificaciones ocurren sobre la copia local. |
| **Por Referencia (Punteros)** | Se envía la *dirección de memoria* (`&`) y se recibe con un puntero (`*`). | Directo — las modificaciones alteran el valor original. |

#### Ejemplo 1 — Paso por valor

```c
#include <stdio.h>

void duplicarPorValor(int numero) {
    numero = numero * 2;
    printf("Dentro de la funcion (Valor): %d\n", numero);
}

int main() {
    int miVariable = 10;
    printf("Antes de la funcion: %d\n", miVariable);
    duplicarPorValor(miVariable);
    printf("Despues de la funcion: %d\n", miVariable); // permanece intacto
    return 0;
}
```

#### Ejemplo 2 — Paso por referencia

```c
#include <stdio.h>

void duplicarPorReferencia(int *numero) {
    *numero = (*numero) * 2;
    printf("Dentro de la funcion (Referencia): %d\n", *numero);
}

int main() {
    int miVariable = 10;
    printf("Antes de la funcion: %d\n", miVariable);
    duplicarPorReferencia(&miVariable); // se envía la dirección de memoria
    printf("Despues de la funcion: %d\n", miVariable); // se altera el original
    return 0;
}
```

---

## 🗂️ 2. Arreglos (Arrays)

Un arreglo es una estructura estática que almacena una colección secuencial de elementos del mismo tipo en bloques de memoria contiguos.

### Tipos de arreglos según su dimensión

| Tipo | Dimensión | ¿Qué es? | Ejemplo de uso |
| :--- | :--- | :--- | :--- |
| **Vector** | Unidimensional (1D) | Una lista simple de elementos ubicados en una sola fila de memoria, accesibles con un único índice `[i]`. | Guardar las edades de un grupo de estudiantes. |
| **Matriz** | Bidimensional (2D) | Una tabla de filas y columnas; cada elemento se accede con dos índices `[fila][columna]`. Es como un arreglo de arreglos. | Representar una hoja de cálculo o un tablero. |
| **Cubo** | Tridimensional (3D) | Una colección de matrices apiladas en "capas"; cada elemento se accede con tres índices `[capa][fila][columna]`. Es un arreglo de matrices. | Modelar datos por capas, como notas de varios estudiantes en distintos periodos. |

### 2.1 Arreglo unidimensional (vector)

```c
#include <stdio.h>

int main() {
    int edades[5] = {18, 21, 25, 19, 22};

    printf("--- Registro de Edades ---\n");
    for (int i = 0; i < 5; i++) {
        printf("Estudiante %d: %d años\n", (i + 1), edades[i]);
    }
    return 0;
}
```

### 2.2 Arreglo bidimensional (matriz)

```c
#include <stdio.h>

int main() {
    int matriz[2][3] = {
        {10, 20, 30},
        {40, 50, 60}
    };

    printf("--- Visualizacion de Matriz ---\n");
    for (int fila = 0; fila < 2; fila++) {
        for (int col = 0; col < 3; col++) {
            printf("[%d] ", matriz[fila][col]);
        }
        printf("\n");
    }
    return 0;
}
```

### 2.3 Arreglo tridimensional (cubo / capas)

```c
#include <stdio.h>

int main() {
    int cubo[2][2][3] = {
        { {1, 2, 3}, {4, 5, 6} },     // Capa 0
        { {7, 8, 9}, {10, 11, 12} }   // Capa 1
    };

    printf("--- Arreglo Tridimensional ---\n");
    for (int capa = 0; capa < 2; capa++) {
        printf("Capa %d:\n", capa);
        for (int fila = 0; fila < 2; fila++) {
            for (int col = 0; col < 3; col++) {
                printf("[%2d] ", cubo[capa][fila][col]);
            }
            printf("\n");
        }
        printf("\n");
    }
    return 0;
}
```

---

## 🧠 3. Reflexión crítica

### Dificultades encontradas

- **Flujo de funciones:** al inicio me costaba visualizar cómo el programa "salta" de `main` a otra función y regresa. Entender la diferencia entre parámetros (lo que la función necesita) y valor de retorno (lo que devuelve) requirió leer el código paso a paso y hacer pruebas de escritorio.
- **Manejo de memoria con punteros:** aprender el paso por referencia me obligó a diferenciar entre modificar una copia temporal y modificar el dato real en memoria usando el operador `&`.
- **Gestión de índices en arreglos:** en los arreglos tridimensionales, el reto fue la complejidad cognitiva de manejar múltiples bucles `for` anidados. Nombrar bien las variables ("capa", "fila", "columna") fue clave para no perderme en la propia lógica.

### Aprendizaje de la Unidad 

* La modularidad no es solo una regla de sintaxis: es una forma de pensar. Aislar el código en funciones fue mi mayor dificultad inicial, pero ahora entiendo que es la única manera de no abrumarse frente a un problema complejo. Dominar arreglos y punteros en C me dio una base sólida sobre cómo se organiza la memoria en programas reales. Ambos conceptos marcan el paso de escribir código que "funciona por casualidad" a diseñar soluciones con una estructura intencional.

---

[← Volver al Portafolio](index.md)

[🏠 Volver al inicio](index.md)

---

<h1 align="center">UNIVERSIDAD NACIONAL DE LOJA</h1>
<p align="center">
<img width="400" height="300" alt="image" src="https://github.com/user-attachments/assets/4435b046-022b-4535-8a37-e107e4a7012c" />
</p>

# PORTAFOLIO DIGITAL — Unidad 2
## Estructuras Condicionales y Repetitivas

| Información Institucional | Datos del Estudiante y Docente |
| :--- | :--- |
| **Institución:** Universidad Nacional de Loja | **Estudiante:** Tyrone Efren Encarnación Erique |
| **Facultad:** Energía, las Industrias y los Recursos Naturales No Renovables | **Docente:** Ing. Lissette Geoconda López Faicán |
| **Carrera:** Ingeniería en Computación | **Ciclo / Paralelo:** Ciclo 1A |
| **Asignatura:** Teoría de la Programación | **Período Académico:** Marzo-agosto 2026 |

---

## Índice

1. [Estructuras Condicionales](#1-estructuras-condicionales)
2. [Estructuras Repetitivas](#2-estructuras-repetitivas)
3. [Ejercicio Integrador](#3-ejercicio-integrador)
4. [Dificultades y Reflexión Crítica](#4-dificultades-y-reflexión-crítica)

---

## 1. Estructuras Condicionales

Las estructuras condicionales permiten que un programa tome decisiones y ejecute distintos bloques de instrucciones según si una condición es verdadera o falsa.

### 1.1 Tipos de estructuras condicionales

#### a) Condicional Simple (`if`)
Ejecuta un bloque de instrucciones **solo si** la condición es verdadera.

**Diagrama de flujo:**
```
        ┌─────────┐
        │  Inicio │
        └────┬────┘
             │
        ┌────▼────────┐
        │  Condición  │──── NO ───┐
        └────┬────────┘           │
            SÍ                    │
        ┌────▼────────┐           │
        │  Acción     │           │
        └────┬────────┘           │
             │◄────────────────────┘
        ┌────▼────┐
        │   Fin   │
        └─────────┘
```

**Pseudocódigo:**
```
INICIO
  leer dato
  SI condición ENTONCES
    ejecutar acción
  FIN_SI
FIN
```

---

#### b) Condicional Doble (`if – else`)
Ejecuta un bloque si la condición es verdadera, y **otro bloque diferente** si es falsa.

**Diagrama de flujo:**
```
        ┌─────────┐
        │  Inicio │
        └────┬────┘
             │
        ┌────▼────────┐
        │  Condición  │
        └──┬──────┬───┘
          SÍ      NO
     ┌────▼───┐ ┌─▼──────┐
     │Acción A│ │Acción B│
     └────┬───┘ └──┬─────┘
          │        │
          └───┬────┘
         ┌────▼────┐
         │   Fin   │
         └─────────┘
```

**Pseudocódigo:**
```
INICIO
  leer dato
  SI condición ENTONCES
    ejecutar acción A
  SINO
    ejecutar acción B
  FIN_SI
FIN
```

---

#### c) Condicional Múltiple (`if – else if – else` / `switch`)
Evalúa varias condiciones en cadena y ejecuta el bloque correspondiente al primer caso verdadero.

**Diagrama de flujo:**
```
        ┌──────────────┐
        │  Condición 1 │──── NO ──► Condición 2 ──── NO ──► Acción C (default)
        └──────┬───────┘            └──────┬───────┘
              SÍ                          SÍ
         ┌────▼──────┐              ┌─────▼──────┐
         │  Acción A │              │  Acción B  │
         └────┬──────┘              └─────┬──────┘
              └──────────────┬────────────┘
                         ┌───▼───┐
                         │  Fin  │
                         └───────┘
```

**Pseudocódigo:**
```
INICIO
  leer opción
  SEGÚN opción HACER
    CASO 1: ejecutar acción A
    CASO 2: ejecutar acción B
    CASO 3: ejecutar acción C
    DEFECTO: ejecutar acción por defecto
  FIN_SEGÚN
FIN
```

---

## 2. Estructuras Repetitivas

Las estructuras repetitivas (bucles o ciclos) permiten ejecutar un conjunto de instrucciones varias veces mientras se cumpla una condición.

### 2.1 Tipos de estructuras repetitivas

#### a) Ciclo `MIENTRAS` (`while`) — Repetición con condición al inicio
Evalúa la condición **antes** de ejecutar el cuerpo. Si la condición es falsa desde el inicio, el bloque nunca se ejecuta.

**Diagrama de flujo:**
```
        ┌─────────┐
        │  Inicio │
        └────┬────┘
             │
        ┌────▼────────┐
     ┌──│  Condición  │── NO ──► Fin
     │  └─────────────┘
     │        SÍ
     │  ┌─────▼──────┐
     │  │   Cuerpo   │
     │  └─────┬──────┘
     └─────────┘
```

**Pseudocódigo:**
```
INICIO
  inicializar contador
  MIENTRAS condición HACER
    ejecutar instrucciones
    actualizar contador
  FIN_MIENTRAS
FIN
```

---

#### b) Ciclo `HACER – MIENTRAS` (`do – while`) — Repetición con condición al final
Ejecuta el cuerpo **al menos una vez** y luego evalúa la condición.

**Diagrama de flujo:**
```
        ┌─────────┐
        │  Inicio │
        └────┬────┘
             │
        ┌────▼──────┐
        │   Cuerpo  │◄──────┐
        └────┬──────┘        │
             │               │
        ┌────▼────────┐      │
        │  Condición  │─ SÍ ─┘
        └─────┬───────┘
              NO
         ┌────▼────┐
         │   Fin   │
         └─────────┘
```

**Pseudocódigo:**
```
INICIO
  HACER
    ejecutar instrucciones
    actualizar contador
  MIENTRAS condición
FIN
```

---

#### c) Ciclo `PARA` (`for`) — Repetición con contador
Se usa cuando se conoce de antemano el número de iteraciones.

**Diagrama de flujo:**
```
        ┌─────────────────────────┐
        │  Inicio: i = valor_ini  │
        └────────────┬────────────┘
                     │
        ┌────────────▼────────────┐
     ┌──│    i <= valor_final     │── NO ──► Fin
     │  └─────────────────────────┘
     │              SÍ
     │  ┌───────────▼────────┐
     │  │      Cuerpo        │
     │  └───────────┬────────┘
     │              │
     │  ┌───────────▼────────┐
     └──│    i = i + paso    │
        └────────────────────┘
```

**Pseudocódigo:**
```
INICIO
  PARA i DESDE valor_inicial HASTA valor_final CON PASO incremento HACER
    ejecutar instrucciones
  FIN_PARA
FIN
```

---

## 3. Ejercicio Integrador

### 3.1 Planteamiento del problema

> **Problema:** Desarrollar un programa que pida al usuario ingresar **10 números enteros**, determine si cada uno es **par o impar**, y al final muestre:
> - La **cantidad de números pares** ingresados.
> - La **cantidad de números impares** ingresados.
> - El **mayor número** ingresado.

---

### 3.2 Análisis del problema

| Elemento | Descripción |
| :--- | :--- |
| **Entradas** | 10 números enteros ingresados por el usuario |
| **Proceso** | Contar pares e impares; comparar para encontrar el mayor |
| **Salidas** | Cantidad de pares, cantidad de impares, mayor número |

**Variables necesarias:**

| Variable | Tipo | Descripción |
| :--- | :--- | :--- |
| `numero` | Entero | Número ingresado en cada iteración |
| `pares` | Entero | Contador de números pares |
| `impares` | Entero | Contador de números impares |
| `mayor` | Entero | Almacena el número mayor encontrado |
| `i` | Entero | Contador del ciclo (1 al 10) |

---

### 3.3 Diseño del algoritmo — Diagrama de flujo

```
              ┌──────────────────────┐
              │        INICIO        │
              └──────────┬───────────┘
                         │
              ┌──────────▼───────────┐
              │ pares ← 0            │
              │ impares ← 0          │
              │ mayor ← -∞ (muy bajo)│
              └──────────┬───────────┘
                         │
              ┌──────────▼───────────┐
              │    i ← 1             │
              └──────────┬───────────┘
                         │
              ┌──────────▼───────────┐
         ┌────│     i <= 10 ?        │──── NO ──────────────────┐
         │    └──────────────────────┘                          │
        SÍ                                                       │
         │                                                       │
    ┌────▼──────────────────┐                                   │
    │  Ingresar número      │                                   │
    └────┬──────────────────┘                                   │
         │                                                       │
    ┌────▼──────────────────┐                                   │
    │  número % 2 == 0 ?    │                                   │
    └──┬──────────────┬─────┘                                   │
      SÍ              NO                                         │
    ┌──▼──────┐   ┌───▼───────┐                                 │
    │pares++  │   │impares++  │                                 │
    └──┬──────┘   └───┬───────┘                                 │
       └──────┬────────┘                                         │
    ┌─────────▼─────────────┐                                   │
    │  número > mayor ?     │                                   │
    └──┬──────────────┬─────┘                                   │
      SÍ              NO                                         │
    ┌──▼────────┐      │                                         │
    │mayor←núm │      │                                         │
    └──┬────────┘      │                                         │
       └────────┬───────┘                                         │
    ┌───────────▼───────┐                                        │
    │    i ← i + 1      │                                        │
    └───────────┬───────┘                                        │
                └──────────────────────────────────────────────► │
                                                                  │
              ┌───────────────────────────────────────────────────▼──┐
              │ Mostrar: pares, impares, mayor                        │
              └───────────────────────────────────────────────────┬──┘
                                                                   │
                                                          ┌────────▼───────┐
                                                          │      FIN       │
                                                          └────────────────┘
```

---

### 3.4 Pseudocódigo

```
INICIO
  pares   ← 0
  impares ← 0
  mayor   ← -999999

  PARA i DESDE 1 HASTA 10 CON PASO 1 HACER
    ESCRIBIR "Ingrese el número ", i, ":"
    LEER numero

    SI numero MOD 2 = 0 ENTONCES
      pares ← pares + 1
    SINO
      impares ← impares + 1
    FIN_SI

    SI numero > mayor ENTONCES
      mayor ← numero
    FIN_SI
  FIN_PARA

  ESCRIBIR "Cantidad de números pares:   ", pares
  ESCRIBIR "Cantidad de números impares: ", impares
  ESCRIBIR "El número mayor ingresado:   ", mayor
FIN
```

---

### 3.5 Codificación — Código fuente en C

```c
/* ============================================================
   Programa  : Clasificador de 10 números (par/impar y mayor)
   Autor     : Tyrone Efren Encarnación Erique
   Asignatura: Teoría de la Programación — Ciclo 1A
   ============================================================ */

#include <stdio.h>

int main() {
    int numero, pares = 0, impares = 0, mayor;
    int i;

    /* Leer el primer número para inicializar mayor */
    printf("Ingrese el numero 1: ");
    scanf("%d", &numero);

    mayor = numero;

    /* Clasificar el primer número */
    if (numero % 2 == 0) {
        pares++;
    } else {
        impares++;
    }

    /* Estructura repetitiva: leer los 9 números restantes */
    for (i = 2; i <= 10; i++) {
        printf("Ingrese el numero %d: ", i);
        scanf("%d", &numero);

        /* Estructura condicional: par o impar */
        if (numero % 2 == 0) {
            pares++;
        } else {
            impares++;
        }

        /* Condicional para encontrar el mayor */
        if (numero > mayor) {
            mayor = numero;
        }
    }

    /* Mostrar resultados */
    printf("\n====== RESULTADOS ======\n");
    printf("Numeros pares ingresados  : %d\n", pares);
    printf("Numeros impares ingresados: %d\n", impares);
    printf("El numero mayor ingresado : %d\n", mayor);

    return 0;
}
```

---

### 3.6 Validación — Prueba de escritorio

**Datos de entrada de prueba:**

| Iteración (i) | Número ingresado | ¿Par o Impar? | Valor de `pares` | Valor de `impares` | Valor de `mayor` |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 4  | Par    | 1 | 0 | 4  |
| 2 | 7  | Impar  | 1 | 1 | 7  |
| 3 | 12 | Par    | 2 | 1 | 12 |
| 4 | 3  | Impar  | 2 | 2 | 12 |
| 5 | 20 | Par    | 3 | 2 | 20 |
| 6 | 15 | Impar  | 3 | 3 | 20 |
| 7 | 8  | Par    | 4 | 3 | 20 |
| 8 | 1  | Impar  | 4 | 4 | 20 |
| 9 | 6  | Par    | 5 | 4 | 20 |
| 10 | 9 | Impar  | 5 | 5 | 20 |

**Salida esperada:**
```
====== RESULTADOS ======
Números pares ingresados  : 5
Números impares ingresados: 5
El número mayor ingresado : 20
```

✅ La prueba de escritorio confirma que el programa produce resultados correctos.

---

## 4. Dificultades y Reflexión Crítica

### 4.1 Principales dificultades encontradas

| # | Dificultad | Descripción |
| :---: | :--- | :--- |
| 1 | **Inicialización de variables** | Al principio existió confusión sobre cómo inicializar `mayor`. En C no existe un valor "nulo" para enteros, por lo que se optó por leer el primer número antes del ciclo y usarlo como valor inicial de `mayor`. |
| 2 | **Diferencia entre `while` y `for`** | Seleccionar el tipo de ciclo correcto según el problema requirió práctica. El ciclo `for` es más adecuado cuando el número de iteraciones es conocido de antemano, como en este ejercicio. |
| 3 | **Uso de `scanf` y `printf` en C** | El manejo de entrada/salida en C requiere especificar el formato (`%d`, `%f`, etc.) y pasar la dirección de memoria con `&` en `scanf`, lo cual resultó confuso en los primeros intentos. |
| 4 | **Traducción del pseudocódigo al código** | Existieron diferencias entre la sintaxis del pseudocódigo académico y la sintaxis real de C, especialmente en la declaración de variables al inicio del bloque y el uso obligatorio de punto y coma. |

### 4.2 Reflexión crítica

El estudio de las estructuras condicionales y repetitivas representa un paso fundamental en la formación como programador, ya que son la base de prácticamente cualquier algoritmo real. Comprender que un programa no siempre sigue un flujo lineal, sino que puede tomar decisiones y repetir acciones, cambia por completo la manera de pensar y resolver problemas.

La elaboración del diagrama de flujo antes de escribir el código demostró ser una práctica muy valiosa: obliga a analizar el problema con claridad antes de preocuparse por la sintaxis. La prueba de escritorio, por su parte, refuerza la capacidad de seguir la lógica del programa manualmente, lo que desarrolla habilidades de depuración y pensamiento lógico.

En conclusión, dominar estas estructuras en un lenguaje como C forja una comprensión profunda de cómo funciona realmente la memoria y la ejecución del programa, sentando las bases para abordar desafíos más complejos en el futuro profesional dentro de la Ingeniería en Computación.

---

[🏠 Volver al inicio](README.md)

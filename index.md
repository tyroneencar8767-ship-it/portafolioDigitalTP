# 📔 PORTAFOLIO DIGITAL: TEORÍA DE LA PROGRAMACIÓN

## 🏛️ CARÁTULA
*   **Institución:** Universidad Nacional de Loja
*   **Facultad:** Energía, las Industrias y los Recursos Naturales No Renovables
*   **Carrera:** Ingeniería en Computación
*   **Asignatura:** Teoría de la Programación
*   **Unidad:** Unidad 1 - Algoritmos y Estructuras Secuenciales
*   **Ciclo / Paralelo:** Ciclo 1A
*   **Período Académico:** Marzo-agosto 2026 modalidad presencial.
*   **Docente:** Ing. Lissette Geoconda López Faicán
*   **Estudiante:** Tyrone Efren Encarnación Erique
*   **Actividad:** Portafolio Digital Evaluación Sumativa (40%)
*   **Lugar y Fecha:** Loja-Ecuador, 2026

# Teoría de la Programación
## Unidad 1

## 📘 Unidad 1 - Contenidos Teóricos

### 1.1 Conceptos Fundamentales
| Concepto | Definición |
| :--- | :--- |
| **Algoritmo** | Conjunto finito y ordenado de instrucciones para resolver un problema. |
| **Pseudocódigo** | Representación textual de un algoritmo usando lenguaje natural y estructuras de programación, sirve para diseñar la lógica antes de codificar. |
| **Diagrama de flujo** | Representación gráfica mediante símbolos normalizados: óvalo (Inicio/Fin), paralelogramo (Entrada/Salida), rectángulo (Proceso), rombo (Decisión) y flechas (flujo). Facilita la comprensión visual de la lógica del programa |
| **Prueba de escritorio** | Técnica manual de validación ejecutando el algoritmo paso a paso con datos de prueba, registrando el valor de cada variable en una tabla, para verificar que el resultado sea el esperado antes de ejecutarlo. |
| **Lenguajes de programación** | Sistemas formales de comunicación con la computadora. Se clasifican en: lenguajes de bajo nivel (ensamblador) y alto nivel (C, Python, Java). C es un lenguaje compilado, eficiente y ampliamente usado en sistemas y PseInt es un pseudolenguaje educativo que simula la ejecución de pseudocódigo. |
| **Programación por bloques** | Paradigma visual en que las instrucciones se representan como piezas encajables (bloques). Herramientas como Scratch permiten aprender lógica sin preocuparse por la sintaxis textual. Es ideal para iniciarse en el pensamiento computacional.  |
### 1.2 Herramientas utilizadas
*   **PseInt:** Entorno gratuito y multiplataforma para escribir y ejecutar pseudocódigo en español. Genera diagramas de flujo automáticamente a partir del pseudocódigo escrito.
Descarga: https://pseint.sourceforge.net/
*   **Lenguaje C:** Lenguaje de programación de propósito general, compilado, creado por Dennis Ritchie (1972). Se programa con editores como Dev-C++, Code::Blocks o VS Code + GCC. Es la base de muchos sistemas operativos y lenguajes modernos.

---

## 💻 UNIDAD 1 - Ejercicio con Estructura Secuencial

### 2.1 Planteamiento del Problema
Calcular el total a pagar en una tienda de ropa. Se aplica un **descuento del 10%** si el subtotal supera los $50, y se cobra el **IVA del 15%**.

### 2.2 Análisis del Problema
*   **Entradas:** Cantidad de artículos (entero), Precio unitario (real).
*   **Proceso:** 
    1. `subtotal = cantidad * precio_unitario`
    2. Si `subtotal > 50` aplicar 10% descuento.
    3. `iva = base * 0.15`
*   **Salidas:** Subtotal, Descuento, IVA y Total.

### 2.3 Diseño del algortimo (Pseudocódigo PseInt)
```text
Algoritmo CalcularCompra
    Escribir "Ingrese la cantidad de artículos:"
    Leer cantidad
    Escribir "Ingrese el precio unitario ($):"
    Leer precio_unitario
    subtotal <- cantidad * precio_unitario
    Si subtotal > 50 Entonces
        descuento <- subtotal * 0.10
    SiNo
        descuento <- 0
    FinSi
    base <- subtotal - descuento
    iva <- base * 0.15
    total <- base + iva

    Escribir "SUBTOTAL: $", subtotal
    Escribir "DESCUENTO: $", descuento
	  Escribir "IVA : $", iva
    Escribir "TOTAL: $", total
FinAlgoritmo
```
#### 2.3.1 Ejemplo de ejecución en PseInt
<img width="1211" height="962" alt="image" src="https://github.com/user-attachments/assets/b3032c25-45d1-4844-b77a-108b2954e728" />

### 2.4 Diseño del algoritmo (Diagrama de flujo PseInt)
<img width="565" height="697" alt="image" src="https://github.com/user-attachments/assets/d152c4e4-240c-4d5c-abd0-858d435990ab" />

### 2.5 Diseño del algoritmo (Codigo en lenguaje C)
```c
#include <stdio.h>

int main() {
    //Variables
    int cantidad;
    float precio_unitario, subtotal, descuento, base, iva, total;

    //Datos de entrada
    printf("Ingrese la cantidad de articulos: ");
    scanf("%d", &cantidad);
    printf("Ingrese el precio unitario ($): ");
    scanf("%f", &precio_unitario);

    //Proceso
    subtotal = cantidad * precio_unitario;

    descuento = (subtotal > 50) ? (subtotal * 0.10) : 0;

    base = subtotal - descuento;
    iva = base * 0.15;
    total = base + iva;
    
    //Datos de Salida
    printf("\n--- Resumen de compra ---\n");
    printf("Subtotal:  $ %.2f\n", subtotal);
    printf("Descuento: $ %.2f\n", descuento);
    printf("IVA (15%%): $ %.2f\n", iva);
    printf("TOTAL:     $ %.2f\n", total);

    return 0;
}
```
#### 2.5.1 Ejemplo de ejecución en lengua C (Usando VS CODE)
<img width="1328" height="1034" alt="image" src="https://github.com/user-attachments/assets/5f3a1201-fafa-4bb2-b922-05b55e4bc867" />


## Unidad 2

## Unidad 3


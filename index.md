

<h1 align="center">UNIVERSIDAD NACIONAL DE LOJA</h1>
<p align="center">
<img width="400" height="300" alt="image" src="https://github.com/user-attachments/assets/4435b046-022b-4535-8a37-e107e4a7012c" />

</p>

<div align="center">
  <p><em>"TEMA DE LA UNIDAD: Fundamentos de Algoritmos y programas"</em></p>
</div>

# PORTAFOLIO DIGITAL: EVALUACIÓN SUMATIVA (40%)

| Información Institucional |  Datos del Estudiante y Docente |
| :--- | :--- |
| **Institución:** Universidad Nacional de Loja | **Estudiante:** Tyrone Efren Encarnación Erique |
| **Facultad:** Energía, las Industrias y los Recursos Naturales No Renovables | **Docente:** Ing. Lissette Geoconda López Faicán|
| **Carrera:** Ingeniería en Computación | **Ciclo / Paralelo:** Ciclo 1A |
| **Asignatura:** Teoría de la Programación | **Período Académico:** Marzo-agosto 2026 |
| **Unidad:** Unidad 1  | **Lugar y Fecha:** Loja-Ecuador, 2026 |

---

# <div align="center"> Teoría de la Programación
## Unidad 1

## 1. Contenidos Teóricos

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

## 2. Ejercicio con Estructura Secuencial

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
#### 2.5.1 Ejemplo de ejecución en lenguaje C (Usando VS CODE)
<img width="1328" height="1034" alt="image" src="https://github.com/user-attachments/assets/5f3a1201-fafa-4bb2-b922-05b55e4bc867" />

## 2.6 Validación: Pruebas de Escritorio

Se han realizado simulaciones manuales para verificar la exactitud de los cálculos antes de la codificación.
#### 2.6.1 Caso 1
**Datos:** Cantidad = 96, Precio Unitario = $5.00
**Subtotal:** $480.00 (Supera los $50, si aplica descuento).

| Paso | Acción | Cantidad | Precio U. | Subtotal | Descuento | Base | IVA (15%) | TOTAL |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | Leer datos | 96 | 5.00 | - | - | - | - | - |
| 2 | Calcular Subtotal | 96 | 5.00 | 480.00 | - | - | - | - |
| 3 | ¿Subtotal > 50? | 96 | 5.00 | **Sí** | - | - | - | - |
| 4 | Calcular Desc (10%)| 96 | 5.00 | 480.00 | 48.00 | - | - | - |
| 5 | Calcular Base | 96 | 5.00 | 480.00 | 48.00 | 432.00 | - | - |
| 6 | Calcular IVA | 96 | 5.00 | 480.00 | 48.00 | 432.00 | 64.80 | - |
| 7 | **Resultado Final** | 96 | 5.00 | 480.00 | 48.00 | 432.00 | 64.80 | **496.80** |

#### 2.6.2 Caso 2
**Datos:** Cantidad = 2, precio Unitario = $20.00 
**Subtotal:** $40.00 (No supera los $50, no aplica descuento)

| Paso | Acción | Cantidad | Precio U. | Subtotal | Descuento | Base | IVA (15%) | TOTAL |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | Leer datos | 2 | 20.00 | - | - | - | - | - |
| 2 | Calcular Subtotal | 2 | 20.00 | 40.00 | - | - | - | - |
| 3 | ¿Subtotal > 50? | 2 | 20.00 | **No** | - | - | - | - |
| 4 | Asignar Descuento | 2 | 20.00 | 40.00 | 0.00 | - | - | - |
| 5 | Calcular Base | 2 | 20.00 | 40.00 | 0.00 | 40.00 | - | - |
| 6 | Calcular IVA | 2 | 20.00 | 40.00 | 0.00 | 40.00 | 6.00 | - |
| 7 | **Resultado Final** | 2 | 20.00 | 40.00 | 0.00 | 40.00 | 6.00 | **46.00** |

### 2.6.3 Caso 3
**Datos:** Cantidad = 3, Precio Unitario = $25.00 
**Subtotal** = $75.00 (Supera los $50, si aplica descuento).

| Paso | Acción | Cantidad | Precio U. | Subtotal | Descuento | Base | IVA (15%) | TOTAL |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | Leer datos | 3 | 25.00 | - | - | - | - | - |
| 2 | Calcular Subtotal | 3 | 25.00 | 75.00 | - | - | - | - |
| 3 | ¿Subtotal > 50? | **SÍ** | 25.00 | 75.00 | - | - | - | - |
| 4 | Aplicar Desc (10%) | 3 | 25.00 | 75.00 | 7.50 | - | - | - |
| 5 | Calcular Base | 3 | 25.00 | 75.00 | 7.50 | 67.50 | - | - |
| 6 | Calcular IVA | 3 | 25.00 | 75.00 | 7.50 | 67.50 | 10.13 | - |
| 7 | **Resultado Final** | 3 | 25.00 | 75.00 | 7.50 | 67.50 | 10.13 | **77.63** |



---

### 3. Principales dificultades encontradas
Durante el desarrollo de las actividades de la Unidad 1, las principales complicaciones técnicas se centraron en los siguientes puntos:  

**Adaptación a la Sintaxis de C:** Presenté dificultades específicas al gestionar los tipos de datos (int, float, char) y el uso correcto de las máscaras de formato (%i, %d, %f, %c) dentro de las funciones de entrada y salida de datos.  
**Depuración de Código Basura:** En varias ocasiones durante la unidad, el programa presentaba líneas de código innecesarias (código basura) que afectaban la limpieza del proyecto, lo que requirió un proceso de depuración más exhaustivo para cumplir con los estándares de programación.  
**Gestión de Salidas:** El control de los formatos de salida (como el uso de %.2f para limitar los decimales) fue un reto inicial para asegurar que la información presentada al usuario fuera precisa y legible.

### 4. Reflexión crítica
El desarrollo de este proyecto ha sido fundamental para comprender que la programación no es solo la escritura de código; representa un proceso riguroso de pensamiento lógico y estructuración mental. He comprendido que el diseño previo de algoritmos y diagramas de flujo es una etapa muy recomendable que reduce significativamente los errores de sintaxis y lógica en lenguaje C. Asimismo, la ejecución de pruebas de escritorio manuales resultó indispensable para validar mi razonamiento antes de la implementación técnica. Más allá de la lógica de programación, esta actividad me permitió adquirir nuevas habilidades en el uso de GitHub como plataforma de control de versiones y el dominio de la sintaxis Markdown. El aprendizaje de diversos componentes y etiquetas (como tablas, fórmulas y jerarquía de títulos) ha sido clave para organizar el contenido de manera técnica, profesional y estructurada, y mediante esto fortaleces habilidades esenciales para mi formación como futuro ingeniero en computación.

---

## 5. Bibliografía (Formato IEEE)
*   [1] B. W. Kernighan y D. M. Ritchie, *El lenguaje de programación C*, México: Prentice Hall, 2021. Disponible: https://lc.fie.umich.mx/~moises/apuntes/Programaci%C3%B3n%20de%20Computadoras/libro_tecto.pdf
*   [2] P. Deitel y H. Deitel, *C: Cómo programar*, 8.ª ed. México: Pearson Educación, 2022. Disponible: https://elhacker.info/manuales/Lenguajes%20de%20Programacion/C++/Como%20programar%20en%20C%20-%20C++%20(Deitel%20-%20Deitel).pdf
*   [3] PseInt Project, "PseInt - Herramienta educativa para pseudocódigo," 2023. Disponible: https://pseint.sourceforge.net/.

---

## 6. Declaración de Uso de IA Generativa
En el desarrollo de este portafolio digital se emplearon herramientas de **Inteligencia Artificial Generativa (Gemini/Claude)** como tutores para reforzar conceptos teóricos de la Unidad 1, optimizar  y estructurar técnicamente el formato Markdown para su correcta visualización en GitHub. El uso de estas tecnologías se limitó estrictamente al apoyo en la maquetación y depuración técnica, garantizando que el planteamiento del problema, el análisis lógico, el diseño y creación del algoritmo y la validación manual mediante pruebas de escritorio fueran realizados, comprendidos y validados íntegramente por el estudiante, asegurando así la autenticidad del proceso de aprendizaje y la autoría de los resultados presentados.



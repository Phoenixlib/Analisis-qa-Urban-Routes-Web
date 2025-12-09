# 🚀 Proyecto de QA: Análisis de Reserva en Urban Routes (Web)

Este repositorio contiene la documentación y los artefactos de pruebas de control de calidad (QA) ejecutadas sobre la funcionalidad de reserva de vehículos (Carsharing) en la plataforma web de Urban Routes.

---

## 📝 Resumen de Análisis y Pruebas QA para Urban Routes (Funcionalidad de Reserva)

### Introducción y Alcance del Proyecto

El objetivo de este proyecto fue realizar un **análisis de calidad (QA)** y una **validación funcional y de diseño (UI/UX)** exhaustiva de las funcionalidades clave de la aplicación web de Carsharing "Urban Routes". Se cubrieron la **interfaz del formulario de reserva**, la **gestión de tarjetas de crédito/débito (Método de Pago)** y la **lógica del botón de reserva** en diferentes estados del formulario.

### 🛠️ Metodología de Pruebas

Se empleó la técnica de **listas de comprobación (Checklist)**, combinada con el diseño y ejecución de **casos de prueba detallados**, para asegurar la cobertura de requisitos de diseño, funcionalidad y lógica de negocio. Las pruebas se ejecutaron principalmente en **Google Chrome** y, para la verificación de diseño inicial, también en **Firefox**.

### 📊 Resultados Clave y Hallazgos

A continuación, se presenta un desglose de las áreas probadas y los principales hallazgos:

#### 1. Pruebas de Diseño (UI/UX) del Formulario de Reserva

Se validaron 79 puntos de diseño, cubriendo la presentación de tarifas, la descripción del vehículo, la disposición del mapa, y el estado de los campos de entrada (**Licencia de Conducir** y **Método de Pago**).

| Tipo de Prueba | Total de Puntos | Aprobados | No Aprobados |
| :--- | :--- | :--- | :--- |
| Diseño y Estilos (Checklist) | 69 | 57 | **12** |

**Hallazgos Críticos de Diseño (Ejemplos):**

* **Fallo de Iconografía:** Ausencia del icono de "persona caminando" junto al subtítulo de la tarifa (TS3-21).
* **Problemas en el Mapa:** Los iconos de automóviles disponibles no se mostraban, ni estaban ordenados según las calles (TS3-22, TS3-23).
* **Elementos de Interacción:** El icono de flecha derecha/check para la licencia de conducir no se mostraba correctamente al inicio/finalizar el proceso (TS3-25, TS3-26).
* **Ventana de Cancelación:** El flujo de cancelación de viaje no mostraba correctamente la ventana de confirmación (TS3-30), lo que impidió la verificación de 7 casos relacionados (Marcados como **OMITIDO**).

#### 2. Pruebas de Lógica en la Ventana de "Método de Pago" (Tarjeta)

Se realizaron pruebas específicas para el formulario de adición de tarjetas, centrándose en las validaciones de los campos **"Número de Tarjeta"** y **"Código"**.

| Tipo de Prueba | Total de Puntos | Aprobados | No Aprobados |
| :--- | :--- | :--- | :--- |
| Validación de Campos (Checklist) | 32 | 22 | **10** |

**Hallazgos Críticos de Validación (Ejemplos):**

* **Límites de Entrada:** El campo **"Número de Tarjeta"** permitía la entrada de más de 12 dígitos, y el campo **"Código"** aceptaba menos de 2 o más de 2 caracteres (TS3-11, TS3-19, TS3-18).
* **Validación de Caracteres:** El campo **"Número de Tarjeta"** aceptaba letras latinas y el campo **"Código"** no deshabilitaba el botón de agregar tarjeta con entradas inválidas (TS3-14, TS3-25, TS3-26).
* **UX/Formato:** El formato automático de espacios en el número de tarjeta no se aplicaba al perder el foco (TS3-15).
* **Flujo de Finalización:** El regreso a la ventana de **"Método de Pago"** tras agregar una tarjeta era incorrecto, no mostrando el *check* azul de tarjeta seleccionada (TS3-31).

#### 3. Pruebas de Lógica del Botón "Reservar" y Flujo de Reserva

Se definieron 5 casos de prueba para validar la lógica y el texto del botón **"Reservar"** en función del estado de los campos obligatorios (**Licencia, Pago, Direcciones**) y 6 casos para la funcionalidad de reserva en sí misma (temporizador, precio, cancelación).

| Área | Total de Casos | Aprobados | No Aprobados |
| :--- | :--- | :--- | :--- |
| Lógica Botón "Reservar" | 5 | 1 | **4** |
| Funcionalidad de Reserva | 6 | 0 | **6** |

**Hallazgos Críticos de Lógica y Funcionalidad:**

* **Botón "Reservar" (TS3-8, TS3-9, TS3-10):** La lógica de validación para el botón falló en 4 de los 5 escenarios probados.
* **Flujo de Reserva Crítico (TS3-1 a TS3-7):** **Ningún caso de prueba de reserva (6/6) se aprobó.** Los fallos incluyen: fallo al mostrar la ventana principal de **"Automóvil reservado"**, problemas con la visualización del **precio total/por minuto** y fallos en el funcionamiento del **temporizador** y el flujo de **cobro/cancelación**.

### Conclusión

Se identificó un total de **22 fallos (Bugs)** que afectan directamente a la **experiencia del usuario (UX)** y a la **funcionalidad principal** de la aplicación, especialmente en los módulos de **reserva de vehículos** y **adición de métodos de pago**. Los informes de error detallados se encuentran enlazados en Jira para su seguimiento y corrección por parte del equipo de desarrollo.

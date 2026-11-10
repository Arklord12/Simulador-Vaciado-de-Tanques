# Simulador de Vaciado de Tanques - Ley de Torricelli 💧

Un simulador interactivo y visual desarrollado para modelar, resolver y comparar el tiempo de vaciado de distintas geometrías de recipientes utilizando ecuaciones diferenciales y la Ley de Torricelli. 

Este proyecto computacional sirve como banco de pruebas virtual para respaldar el diseño de modelos físicos (como contenedores cónicos en PETG impresos en 3D), permitiendo optimizar geometrías para evacuar volúmenes específicos (ej. 750 mL) en el menor tiempo posible a través de restricciones de salida milimétricas (ej. orificios de 1/8 de pulgada).

## 🚀 Características Principales

* **Llenado Parcial Dinámico:** Permite ingresar el volumen exacto de líquido a evaluar. El motor calcula matemáticamente la altura inicial ($h_0$) del fluido basándose en la geometría total del tanque antes de iniciar el vaciado.
* **Manejo de Geometrías Truncadas:** Modelado exacto del área transversal $A(h)$ para el corte del orificio inferior en:
  * Cilindro Recto
  * Cono Invertido Truncado
  * Paraboloide Truncado
* **Integración Numérica (Método de Euler):** Resolución iterativa de la ecuación de balance volumétrico paso a paso hasta que el nivel del agua llega a cero.
* **Precisión de Calibre:** Soporte para inputs de alta precisión (hasta 4 decimales) en el radio del orificio para modelar agujeros de drenaje reales.
* **Visualización y Analítica en Tiempo Real:** 
  * Animación 2D del fluido y el chorro de salida generada con **HTML5 Canvas**.
  * Gráficas de *Volumen vs. Tiempo* y *Caudal vs. Tiempo* generadas dinámicamente con **Chart.js**.

## 📐 Modelo Matemático

El núcleo del simulador resuelve la siguiente ecuación diferencial derivada de la conservación de la energía (Ley de Torricelli):

```math
\frac{dh}{dt} = - \frac{C_d \cdot a \cdot \sqrt{2gh}}{A(h)}

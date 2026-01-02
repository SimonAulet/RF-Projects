# 1. Antena Dipolo de Media Onda ($\lambda / 2$) - Sintonizado

**Configuración:** Dipolo delgado alimentado en el centro, orientado en $Z$. Dimensiones finales optimizadas mediante *parameter sweep*.

### Parámetros en $1\,\text{GHz}$


| Parámetro | Valor |
| :--- | :--- |
| **Frecuencia de resonancia** | $1.000\,\text{GHz}$ |
| **$S_{11}$ mínimo (Return Loss)** | $-28.0\,\text{dB}$ |
| **Directividad máxima** | $2.119\,\text{dBi}$ |
| **Eficiencia total** | $-0.1715\,\text{dB}$ ($\sim 96\%$) |
| **Eficiencia de radiación** | $0.001466\,\text{dB}$ ($\sim 99.9\%$) |
| **Ancho de haz ($-3\,\text{dB}$) - Plano $E$** | 78.3 $^\circ$ |
| **Ancho de haz ($-3\,\text{dB}$) - Plano $H$** | Omnidireccional |

### Resultados y Análisis de Simulación

#### Optimización y Respuesta en Frecuencia

![Parámetro $S_{11}$ con *parameter sweep*](img/dipolo_S11.png)

**Figura 1.1 - Optimización de impedancia.** Curva del parámetro $S_{11}$ para el factor de longitud óptimo (**$0.463333\lambda$**), obtenido tras un barrido paramétrico (mult. de $0.45$ a $0.49\lambda$). El mínimo de **$-28\,\text{dB}$ a $1\,\text{GHz}$** confirma una sintonía precisa y una adaptación de impedancia óptima.

#### Patrón de Radiación 3D y Cortes Principales

![Diagrama de Directividad 3D (escala log.)](img/dipolo_3D.png)



**Figura 1.2 - Patrón de radiación 3D.** Visualización en escala logarítmica de la directividad. Muestra el patrón toroidal ("donut") característico, con máximos en el plano ecuatorial $(XY)$ y nulos en el eje del dipolo $(Z)$. Se indican los valores de directividad ($2.119\,\text{dBi}$) y eficiencias.

<table>
<tr>
<td width="50%">
<img src="img/dipolo_E-field.png" alt="Corte Plano E" style="width:100%;">
<p style="text-align: center;"><em>Figura 1.3 - Corte Plano $E$ ($\phi=0^\circ$)</em></p>
</td>
<td width="50%">
<img src="img/dipolo_H-field.png" alt="Corte Plano H" style="width:100%;">
<p style="text-align: center;"><em>Figura 1.4 - Corte Plano $H$ ($\theta=90^\circ$)</em></p>
</td>
</tr>
</table>
**Figura 1.3 & 1.4 - Patrones en planos $E$ y $H$.** El corte en el **Plano $E$** (que contiene al dipolo) muestra el diagrama clásico de dos lóbulos. El corte en el **Plano $H$** (perpendicular al dipolo) valida la omnidireccionalidad teórica. Estos resultados corresponden a la longitud de dipolo sintonizada ($0.463333\lambda$).

### Conclusión del Diseño
El dipolo fue modelado y **optimizado sistemáticamente mediante un *parameter sweep* de su longitud**, logrando una resonancia precisa a $1\,\text{GHz}$ con un **$S_{11}$ de $-28\,\text{dB}$**. El patrón de radiación obtenido coincide con la teoría, presentando una **directividad de $2.12\,\text{dBi}$** y eficiencias superiores al $96\%$, validando la calidad de la simulación y el proceso de sintonía.

---

## 2. Antena Helicoidal en Modo Axial (RHCP)

**Configuración de diseño:** Antena helicoidal de $N=5$ vueltas, optimizada para polarización circular derecha (RHCP - *Right-Hand Circular Polarization*) en la frecuencia objetivo de $f = 1\,\text{GHz}$ $(\lambda \approx 300\,\text{mm})$.
*   **Geometría objetivo:** Diámetro $D = \lambda/\pi \approx 95.5\,\text{mm}$, paso $S = \lambda/4 \approx 75.0\,\text{mm}$.
*   **Entorno:** Alimentada sobre un plano de tierra de diámetro $\lambda/2$, construida en PEC (*Perfect Electric Conductor*).

### 2.1 Verificación del Modo de Operación y Eficiencia

El modo axial (o *end-fire*) se caracteriza por un lóbulo principal direccional a lo largo del eje de la hélice y una polarización circular de alta calidad en esa dirección.

![Patrón de radiación 3D de la antena helicoidal](img/helix-3D.png)
*Figura 2.1: Diagrama de radiación 3D en $1\,\text{GHz}$. El patrón muestra un lóbulo principal pronunciado en la dirección del eje (eje $Z$), confirmando la operación en **modo axial**. Los parámetros clave de eficiencia y directividad se detallan en la inspección.*

**Parámetros clave extraídos de la simulación:**
*   **Directividad máxima:** $\mathbf{9.13\,\text{dBi}}$
*   **Eficiencia de radiación:** $\mathbf{-0.002\,\text{dB}}$ $( \approx 99.95\% )$
*   **Eficiencia total:** $\mathbf{-1.55\,\text{dB}}$ $( \approx 70\% )$. La diferencia sugiere pérdidas por desadaptación de impedancia.

### 2.2 Análisis del Patrón de Radiación y Polarización

<table>
<tr>
<!-- Celda para el Patrón de Potencia (Theta) -->
<td width="50%">
<img src="img/helix-axial.png" alt="Corte del patrón de radiación en el plano axial" style="width:100%;">
<p style="text-align: center;"><em>Figura 2.2: Corte del patrón de radiación (Plano axial, variando $\theta$)</em></p>
</td>
<!-- Celda para la Relación Axial (Axial Ratio) -->
<td width="50%">
<img src="img/helix-rel-axial.png" alt="Relación Axial (Axial Ratio) en el plano axial" style="width:100%;">
<p style="text-align: center;"><em>Figura 2.3: Relación Axial (Axial Ratio) en el mismo plano</em></p>
</td>
</tr>
</table>

**Análisis conjunto de las figuras 2.2 y 2.3:**
*   **Directividad y haz principal:** La Figura 2.2 cuantifica el lóbulo principal. Se obtiene una **directividad de $9.13\,\text{dBi}$** con un **ancho de haz a $-3\,\text{dB}$ de $54.8^\circ$**. El nivel de lóbulo lateral es de $-7.2\,\text{dB}$.
*   **Calidad de la polarización circular:** La Figura 2.3 es crítica. Muestra la **Relación Axial (AR)**. En la dirección de máxima radiación $(\theta = 0^\circ)$, el **AR es cercano a $0\,\text{dB}$**, lo que indica una polarización circular casi perfecta. Este valor se mantiene bajo (generalmente por debajo de $3\,\text{dB}$, el umbral usual para "circular") dentro de un cono angular alrededor del eje, degradándose a unos $4\,\text{dB}$ en direcciones laterales. Esto verifica que la antena genera **RHCP de alta calidad en el lóbulo principal**.

### 2.3 Patrón en el Plano Transversal

![Patrón de radiación en el plano transversal (vista desde arriba)](img/helix-superior.png)
*Figura 2.4: Corte del patrón en el plano transversal (plano $XY$, variando $\phi$ a $\theta = 90^\circ$). Este plano, perpendicular al eje de la antena, muestra una directividad significativamente menor ($-2.51\,\text{dBi}$) y un patrón casi omnidireccional (ancho de haz de $328.5^\circ$), como es típico en el modo axial. Confirma que la radiación se concentra en el eje, no en los costados.*

### 2.4 Conclusión del Diseño

La antena simulada cumple con los objetivos de diseño:
1.  Opera en el **modo axial** deseado, con un lóbulo principal direccional de $9.13\,\text{dBi}$ y un ancho de haz de $54.8^\circ$.
2.  Logra **polarización circular derecha (RHCP) de alta calidad** en la dirección del haz principal, evidenciada por una Relación Axial $\approx 0\,\text{dB}$ en el eje.
3.  La geometría construida $(D, S, N)$ demuestra ser efectiva para generar el modo de operación objetivo en la frecuencia de $1\,\text{GHz}$.

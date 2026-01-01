# 1. Antena Dipolo de Media Onda ($\lambda / 2$)

**Configuración de simulación:** Dipolo delgado resonante, orientado a lo largo del eje Z, alimentado en su centro mediante un puerto discreto.

### 1.1 Diagrama de Radiación 3D y Patrones Fundamentales

<!-- Imagen 1: Diagrama 3D -->
![Diagrama de radiación 3D del dipolo](img/dipolo-3D.png)
*Figura 1.1: Patrón de radiación tridimensional característico de un dipolo de media onda. Se observa la forma toroidal (en "donut") con nulos de radiación en la dirección del eje del dipolo (Z) y máximo en el plano ecuatorial (XY).*

<!-- Tabla para Patrones E y H -->
<table>
<tr>
<!-- Celda para el Patrón E -->
<td width="50%">
<img src="img/dipolo-E-field.png" alt="Patrón en el Plano E" style="width:100%;">
<p style="text-align: center;"><em>Figura 1.2: Corte en el Plano E ($\phi = 0 = 90°$)</em></p>
</td>
<!-- Celda para el Patrón H -->
<td width="50%">
<img src="img/dipolo-H-field.png" alt="Patrón en el Plano H" style="width:100%;">
<p style="text-align: center;"><em>Figura 1.3: Corte en el Plano H ($\theta = 90°$)</em></p>
</td>
</tr>
</table>

*Análisis:* El patrón en el **Plano E** (que contiene al dipolo) muestra el clásico diagrama de dos lóbulos, mientras que el **Plano H** (perpendicular al dipolo) confirma la radiación omnidireccional esperada. Estos cortes validan la correcta simulación de los campos fundamentales.

### 1.2 Análisis de Ancho de Banda vs. Relación Longitud/Diámetro (L/D)

**Objetivo:** Evaluar el efecto del grosor del dipolo (simulado mediante la relación longitud/diámetro, L/D) en su ancho de banda, determinándose $-10dB$ como una adaptación óptima.

<!-- Imagen 3: S11 comparativo para diferentes L/D -->
![Comparativa de S11 para diferentes relaciones L/D](img/dipolo_ancho-S11.png)
*Figura 1.5: Superposición de las curvas S11 para dipolos con relaciones L/D de 1000, 50 y 25. Se observa claramente cómo al aumentar el grosor (disminuir L/D) el ancho de banda se incrementa, a costa de un ligero desplazamiento en la frecuencia de resonancia.*

**Resultados Cuantitativos del Ancho de Banda (BW @ S11 < -10 dB):**

  -   **L/D = 1000 (Dipolo delgado):** `4 MHz`
  -   **L/D = 50:** `99 MHz`
  -   **L/D = 25 (Dipolo grueso):** `121 MHz`

La simulación confirma el principio teórico de que **dipolos más gruesos (menor relación L/D) presentan un mayor ancho de banda de impedancia**

---

## 2. Antena Helicoidal en Modo Axial (RHCP)

**Configuración de diseño:** Antena helicoidal de $N=5$ vueltas, optimizada para polarización circular derecha (RHCP - *Right-Hand Circular Polarization*) en la frecuencia objetivo de $f = 1 \, \text{GHz}$ $(\lambda \approx 300 \, \text{mm})$.
*   **Geometría objetivo:** Diámetro $D = \lambda/\pi \approx 95.5 \, \text{mm}$, paso $S = \lambda/4 \approx 75.0 \, \text{mm}$.
*   **Entorno:** Alimentada sobre un plano de tierra de diámetro $\lambda/2$, construida en PEC (*Perfect Electric Conductor*).

### 2.1 Verificación del Modo de Operación y Eficiencia

El modo axial (o *end-fire*) se caracteriza por un lóbulo principal direccional a lo largo del eje de la hélice y una polarización circular de alta calidad en esa dirección.

![Patrón de radiación 3D de la antena helicoidal](img/helix-3D.png)
*Figura 2.1: Diagrama de radiación 3D en $1 \, \text{GHz}$. El patrón muestra un lóbulo principal pronunciado en la dirección del eje (eje Z), confirmando la operación en **modo axial**. Los parámetros clave de eficiencia y directividad se detallan en la inspección.*

**Parámetros clave extraídos de la simulación:**
*   **Directividad máxima:** $\mathbf{9.13 \, \text{dBi}}$
*   **Eficiencia de radiación:** $\mathbf{-0.002 \, \text{dB}}$ $( \approx 99.95\% )$
*   **Eficiencia total:** $\mathbf{-1.55 \, \text{dB}}$ $( \approx 70\% )$. La diferencia sugiere pérdidas por desadaptación de impedancia.

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
*   **Directividad y haz principal:** La Figura 2.2 cuantifica el lóbulo principal. Se obtiene una **directividad de $9.13 \, \text{dBi}$** con un **ancho de haz a -3 dB de $54.8^\circ$**. El nivel de lóbulo lateral es de $-7.2 \, \text{dB}$.
*   **Calidad de la polarización circular:** La Figura 2.3 es crítica. Muestra la **Relación Axial (AR)**. En la dirección de máxima radiación $(\theta = 0^\circ)$, el **AR es cercano a $0 \, \text{dB}$**, lo que indica una polarización circular casi perfecta. Este valor se mantiene bajo (generalmente por debajo de $3 \, \text{dB}$, el umbral usual para "circular") dentro de un cono angular alrededor del eje, degradándose a unos $4 \, \text{dB}$ en direcciones laterales. Esto verifica que la antena genera **RHCP de alta calidad en el lóbulo principal**.

### 2.3 Patrón en el Plano Transversal

![Patrón de radiación en el plano transversal (vista desde arriba)](img/helix-superior.png)
*Figura 2.4: Corte del patrón en el plano transversal (plano XY, variando $\phi$ a $\theta = 90^\circ$). Este plano, perpendicular al eje de la antena, muestra una directividad significativamente menor ($-2.51 \, \text{dBi}$) y un patrón casi omnidireccional (ancho de haz de $328.5^\circ$), como es típico en el modo axial. Confirma que la radiación se concentra en el eje, no en los costados.*

### 2.4 Conclusión del Diseño

La antena simulada cumple con los objetivos de diseño:
1.  Opera en el **modo axial** deseado, con un lóbulo principal direccional de $9.13 \, \text{dBi}$ y un ancho de haz de $54.8^\circ$.
2.  Logra **polarización circular derecha (RHCP) de alta calidad** en la dirección del haz principal, evidenciada por una Relación Axial $\approx 0 \, \text{dB}$ en el eje.
3.  La geometría construida $(D, S, N)$ demuestra ser efectiva para generar el modo de operación objetivo en la frecuencia de $1 \, \text{GHz}$.
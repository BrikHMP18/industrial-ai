# Feature Engineering en Dominio de la Frecuencia

Resumen de las principales features extraídas de señales tras FFT (vibraciones, audio, sensores).

---

## 1. Transformación Base

- **FFT** → espectro de magnitud `|FFT(signal)|` o potencia `|FFT|²`
- Para señales reales: usar solo la mitad positiva del espectro

---

## 2. Features Espectrales

| Feature | Qué mide |
|---------|----------|
| **spectral_mean/max/min/std/median** | Estadísticos del espectro |
| **spectral_centroid** | Frecuencia "centro de masa" ponderada → graves vs agudos |
| **spectral_bandwidth** | Dispersión alrededor del centroide → tono vs ruido |
| **spectral_entropy** | Aleatoriedad (Shannon) → periódico vs ruido blanco |
| **spectral_flatness** | GM/AM → 1=ruido, 0=tono puro |
| **spectral_roll_off** | Frecuencia bajo la cual está X% de la energía (ej. 95%) |
| **median_freq** | Frecuencia que divide energía en 50/50 |
| **peak_freq** | Frecuencia del máximo de magnitud |
| **dominant_harmonics_ratio** | Energía en primeros armónicos / total |

---

## 3. Features de Forma

| Feature | Qué mide |
|---------|----------|
| **kurtosis** | Peso de colas → picos vs espectro plano |
| **skewness** | Asimetría → más energía en bajas o altas |
| **IQR** | Dispersión robusta (Q3−Q1) |

---

## 4. Otras

| Feature | Qué mide |
|---------|----------|
| **total_energy** | Nivel global de la señal |
| **band_energy_ratio** | Energía por bandas (bajas/medias/altas) |
| **spectral_flux** | Cambio entre ventanas consecutivas |

**Técnicas**: MFCCs (audio), filtros pasabaja/pasabanda pre-FFT, ventanas Hann/Hamming.

---

## 5. Pipeline Típico

1. Preprocesar (NaN, detrend)
2. Segmentar en ventanas
3. FFT → espectro de magnitud
4. Extraer features por ventana
5. Tratar Inf/NaN, escalar (StandardScaler)
6. Modelar (clasificación, detección de anomalías)

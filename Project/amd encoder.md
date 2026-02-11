# OBS – Configuración AMD HW H.264 (AVC)

> Configuración real usada con **AMD RX 6600** para mejorar estabilidad de bitrate y reducir artefactos en streaming (especialmente en **Twitch**).

---

## 📌 Contexto

Gracias a **AMD**, muchos tenemos la oportunidad de jugar con una **buena relación precio/rendimiento**. Gráficas como la **RX 6600** compiten directamente con una **RTX 3060**, a un precio menor y con rendimiento igual o incluso superior en varios juegos.

Sin embargo, AMD **no tiene un encoder dedicado tipo NVENC**. El encoder **AMF (H.264)** no aprovecha los recursos de la GPU, lo que provoca:

* Peor calidad incluso en bitrate bajo y resolucion alta
* Más artefactos o pixelacion excesiva en movimiento
* Menor eficiencia para streaming + grabación + juego

Aunque es posible transmitir en **4K**, la calidad **no se aprovecha** debido a las limitaciones del bitrate y del encoder.

---

## 🎯 Objetivo de esta configuración

* ✔ Menos pixelado en movimiento
* ✔ Mejor control del bitrate
* ✔ Stream más estable
* ✔ Ideal para RX 6600 / RX 6650 XT / RX 6700

> ⚠️ Sacrifica un poco de calidad teórica para lograr **mejor calidad percibida**,

---

## 🔓 Importante – Twitch

Para que esta configuración funcione correctamente:

👉 **Activar** `Ignorar las recomendaciones del servicio`

Esto permite transmitir a **8000–8500 Kbps**, mejorando notablemente la calidad en escenas con movimiento.

---

## ⚙️ Configuración OBS

### 🔧 Modo de salida

* **Modo de salida:** Avanzado

#### Video

* **Codificador de video:** AMD HW H.264 (AVC)
* **Escalado de salida:** Bicúbico (Escalado fino, 16 muestras)
* **Resolución de salida:** 1920×1080 - 1664x936
* **FPS:** 60 - 30

### ⚙️ Ajustes de codificación

| Opción                        | Valor         |
| ----------------------------- | ------------- |
| Control de la frecuencia      | HQCBR         |
| Tasa de bits                  | **8500 Kbps** |
| Intervalo de fotogramas clave | 0 s (Auto)    |
| Preajuste                     | Equilibrado   |
| Perfil                        | High          |
| Pre-Analysis                  | Activado      |
| Máximos B-frames              | 1             |

---

## 🧠 Opciones avanzadas AMF (Encoder AMD)

```
MaxNumRefFrames=4
BReferenceEnable=1
BPicturesPattern=1
MaxConsecutiveBPictures=1
HighMotionQualityBoostEnable=1
EnableVBAQ=false
RateControlPreanalysisEnable=0
AdaptiveMiniGOP=false
RateControlSkipFrameEnable=false
EnablePreAnalysis=true
PASceneChangeDetectionEnable=false
PATemporalAQMode=1
PAFrameSadEnable=true
HalfPixel=true
QuarterPixel=true
DeBlockingFilter=true
FillerDataEnable=true
```

---

## 🧩 Conclusión

Si usas **AMD RX 6600** y haces streaming en Twitch, esta configuración es una de las formas más **realistas y funcionales** de obtener un stream limpio.

No se trata de la mejor calidad técnica, sino de la **mejor calidad visible posible** con las limitaciones actuales del encoder AMD.

---

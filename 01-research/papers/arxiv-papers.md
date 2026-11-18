# Papers primarios — arXiv (Informe del agente de investigación)

## 1. Repurposing Discarded Smartphones to Minimize Carbon
- **Autores:** investigación universitaria (proyecto "junkyard computers")
- **Año:** 2021-10-13 (v2)
- **ID arXiv:** arXiv:2110.06870v2
- **URL:** https://arxiv.org/abs/2110.06870v2
- **Enfoque:** Reutiliza smartphones desechados (Pixel 3A y Nexus 4) como "junkyard computers" / cloudlet de computación en la nube. Sustituye Android por Ubuntu Touch con kernel modificado para soportar Docker, organiza los teléfonos en Docker Swarm (DeathStarBench como carga de trabajo), y propone la métrica **Computational Carbon Intensity (CCI)**.
- **Métricas clave:**
  - Consumo: Pixel 3A ≈ 0.8 W idle / 1.4–2.5 W bajo carga; promedio 1.54 W.
  - Cloudlet de 10 Pixel 3A cuesta $1,027.60 USD en 3 años vs $40,404 USD de una c5.9xlarge.
  - Eficiencia de carbono: 18.9× más eficiente (SocialNetwork-Write), 9.8× (SocialNetwork-Read), 12.6× (HotelReservation) vs c5.9xlarge.
  - Throughput: hasta 4,000 QPS (HotelReservation).

## 2. Scalable Smartphone Cluster for Deep Learning
- **Autores:** investigación en clúster de smartphones para entrenamiento de DNN
- **Año:** 2021-10-23
- **ID arXiv:** arXiv:2110.12172
- **URL:** https://arxiv.org/abs/2110.12172
- **Enfoque:** Clúster escalable de smartphones para entrenamiento de redes neuronales profundas. Conecta 138 dispositivos Galaxy S10+ mediante tres switchs Ethernet de 48 puertos. Implementa entrenamiento síncrono a gran escala (data parallelism) sobre Caffe con OpenMPI y operación allreduce basada en anillo (RAR). Compilación cruzada en Termux para los chips AP.
- **Métricas clave:**
  - 90% de la velocidad de una NVIDIA P100 entrenando ResNet-50.
  - ≈43× speed-up sobre una NVIDIA V100 entrenando MobileNet-v1.
  - Conexiones Ethernet >2× más rápidas y estables que Wi-Fi 5 GHz.

## 3. More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs
- **Autores:** investigación de SoC Cluster como servidor de borde
- **Año:** 2024-07-17 (subida original 2022-12)
- **ID arXiv:** arXiv:2212.12842
- **URL:** https://arxiv.org/html/2212.12842
- **Enfoque:** Nuevo tipo de servidor de borde llamado **SoC Cluster**, que orquesta múltiples SoCs móviles de bajo consumo. Prototipo de 60 Qualcomm Snapdragon 865 en un rack 2U, desplegado en clouds de borde (cloud gaming).
- **Métricas clave:**
  - Hasta 6.5× más throughput por unidad de energía para inferencia DL vs servidor con NVIDIA A40; comparable a NVIDIA A100.
  - ResNet-50 quantizado: 8.8 ms de latencia de inferencia por SoC.
  - SoC GPUs: ≈18 fps/J en ResNet-50 (FP32) = 7.09× vs Intel CPU, 1.78× vs A40, 1.15× vs A100.

## 4. Reinforcing Edge Computing with Multipath TCP Enabled Mobile Device Clouds
- **Autores:** propuesta de Mobile Device Cloud (MDC) con MPTCP
- **Año:** 2019-09-12 (v2)
- **ID arXiv:** arXiv:1909.05530v2
- **URL:** https://arxiv.org/html/1909.05530v2
- **Enfoque:** Mobile Device Cloud (MDC) habilitado con Multi-Path TCP (MPTCP). Aprovecha múltiples interfaces de radio (celular, Wi-Fi, Bluetooth) para aumentar el throughput y garantizar conectividad robusta.
- **Métricas clave:**
  - Más de 63% de mejora en requests servidos con congestion handler vs sin él.
  - Reducción de dropped requests a un nivel bajo y constante.

## Papers adicionales relacionados (mencionados, no desarrollados)
- **Phone2Cloud** (arXiv:2008.05851, 2020): offloading de computación de smartphones a la nube para ahorro de energía en Android + Hadoop.
- **CROWDio** (arXiv:2604.19363, 2026): framework de Mobile Crowd Computing sobre 6 dispositivos Android; 5.1× speedup vs mejor dispositivo individual y 56.9% de reducción de tiempo vs round-robin.
- **Memory-Efficient Partitioned DNN Inference on Resource-Constrained Android Crowds** (arXiv:2605.20723v1, 2026): particionamiento de ONNX/DistilBERT entre 5 Android handsets vía Wi-Fi.
- **Cloud Offloading for Multi-Radio Enabled Mobile Devices** (arXiv:1511.03698, 2015): offloading por múltiples interfaces de radio (Wi-Fi/LTE) en HTC Vivid.

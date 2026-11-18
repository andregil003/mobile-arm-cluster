# Los 10 papers primarios — Bibliografía Semana 2 (PI3)

Tema: Reutilización de granja de celulares para cluster ARM
Todos los papers son primarios (conferencia, revista IEEE/ACM, arXiv, repositorio universitario) y verificables con URL/DOI.

---

## 1. Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon
- **Autores:** Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto (UC San Diego)
- **Año:** 2023 (conferencia); preprint arXiv octubre 2021
- **Conferencia:** ASPLOS '23 — ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Vol. 2, pp. 400–412, Vancouver, BC
- **URL/DOI:** https://arxiv.org/abs/2110.06870 (DOI: 10.48550/arXiv.2110.06870)
- **Enfoque:** Reutiliza smartphones desechados como "junkyard computers" para evitar fabricar nuevos. Introduce la métrica Computational Carbon Intensity (CCI). Cloudlet real de Pixel 3A (eBay, $65 USD) evaluado con DeathStarBench.
- **Métricas clave:** Pixel 3A: 2.5 W (100% CPU), 0.8 W (idle), 1.54 W promedio; Nexus 4: 3.6 W / 0.7 W / 1.78 W. Fabricación = 70–85% de la huella de carbono de por vida. CCI = (C_M + C_C + C_N) / ops a lo largo de la vida.

## 2. DroidCluster: Towards Smartphone Cluster Computing — The Streets are Paved with Potential Computer Clusters
- **Autores:** Felix Büsching, Sebastian Schildt, Lars C. Wolf (TU Braunschweig, Alemania)
- **Año:** 2012
- **Conferencia:** 2012 32nd International Conference on Distributed Computing Systems Workshops (ICDCSW), pp. 114–117 (IEEE)
- **URL/DOI:** DOI: 10.1109/ICDCSW.2012.59 ; PDF: https://www.ibr.cs.tu-bs.de/papers/buesching-icdcs2012.pdf
- **Enfoque:** Clúster de seis teléfonos Android ejecutando MPI sobre WiFi. Benchmark LINPACK. Concluye que montar un clúster de smartphones es posible y razonable.
- **Métricas clave:** Seis teléfonos Android (LG P500, ARM11 600 MHz). Interconexión solo WiFi (punto de acceso permite teóricamente hasta 1024 nodos). LINPACK sobre WiFi.

## 3. Energy- and Cost-Efficiency Analysis of ARM-Based Clusters
- **Autores:** Zhonghong Ou, B. Pang, Y. Deng, J. K. Nurminen, A. Ylä-Jääski, P. Hui (Aalto / HKUST)
- **Año:** 2012
- **Conferencia:** 12th IEEE/ACM International Symposium on Cluster, Cloud and Grid Computing (CCGrid 2012), Ottawa
- **URL/DOI:** DOI: 10.1109/CCGRID.2012.84 ; PDF: https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1074.9789&rep=rep1&type=pdf
- **Enfoque:** Analiza clúster ARM vs estación de trabajo Intel x86 en eficiencia energética y costo. Concluye que clústeres ARM son significativamente más eficientes energéticamente.
- **Métricas clave:** Ratio de eficiencia energética ARM vs Intel: **2.6x–9.5x**. Eficiencia pico: **1,046 MFLOPS/W**. Consumo total al máximo: ~14 W. Clúster C: 7.101 Gflops con 8 nodos a 25 W → ~284 MFLOPS/W.

## 4. Scalable Smartphone Cluster for Deep Learning
- **Autores:** Byunggook Na, Jaehee Jang, Seongsik Park, Seijoon Kim, Joonoo Kim, Moon Sik Jeong, Kwang Choon Kim, Seon Hee, Yoonsang Kim, Sungroh Yoon
- **Año:** 2021
- **Conferencia:** arXiv preprint (cs.LG / cs.DC)
- **URL/DOI:** https://arxiv.org/abs/2110.12172 (DOI: 10.48550/arXiv.2110.12172)
- **Enfoque:** Cluster de smartphones escalable para entrenamiento de DNN, conectando 138 dispositivos Galaxy S10+ mediante red cableada Ethernet. Entrenamiento síncrono de gran lote con Caffe.
- **Métricas clave:** 138 dispositivos Galaxy S10+ interconectados por Ethernet cableado; 90% de la velocidad de una GPU NVIDIA P100 en ResNet-50; ~43x speed-up sobre una GPU NVIDIA V100 en MobileNet-v1; límite inalámbrico ~30 smartphones.

## 5. More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs
- **Autores:** investigación de SoC Cluster como servidor de borde
- **Año:** 2024-07-17 (subida original 2022-12)
- **Conferencia:** arXiv preprint
- **URL/DOI:** https://arxiv.org/html/2212.12842
- **Enfoque:** Nuevo tipo de servidor de borde llamado **SoC Cluster**, que orquesta múltiples SoCs móviles de bajo consumo. Prototipo de 60 Qualcomm Snapdragon 865 en un rack 2U, desplegado en clouds de borde (cloud gaming).
- **Métricas clave:** Hasta 6.5× más throughput por unidad de energía para inferencia DL vs servidor con NVIDIA A40; comparable a NVIDIA A100. ResNet-50 quantizado: 8.8 ms de latencia de inferencia por SoC. SoC GPUs: ≈18 fps/J en ResNet-50 (FP32).

## 6. Reinforcing Edge Computing with Multipath TCP Enabled Mobile Device Clouds
- **Autores:** propuesta de Mobile Device Cloud (MDC) con MPTCP
- **Año:** 2019-09-12 (v2)
- **Conferencia:** arXiv preprint
- **URL/DOI:** https://arxiv.org/html/1909.05530v2
- **Enfoque:** Mobile Device Cloud (MDC) habilitado con Multi-Path TCP (MPTCP). Aprovecha múltiples interfaces de radio (celular, Wi-Fi, Bluetooth) para aumentar el throughput y garantizar conectividad robusta.
- **Métricas clave:** Más de 63% de mejora en requests servidos con congestion handler vs sin él. Reducción de dropped requests a un nivel bajo y constante.

## 7. Towards Resource Sharing in Mobile Device Clouds: Power Balancing Across Mobile Devices
- **Autores:** Abderrahmen Mtibaa, Afnan Fahim, Khaled A. Harras, Mostafa H. Ammar (Texas A&M, Carnegie Mellon Qatar, Georgia Tech)
- **Año:** 2013
- **Conferencia:** SIGCOMM Mobile Cloud Computing (MCC) workshop 2013
- **URL/DOI:** https://conferences.sigcomm.org/sigcomm/2013/papers/mcc/p51.pdf
- **Enfoque:** Define Mobile Device Cloud (MDC) como offloading computacional realizado entre un conjunto de dispositivos móviles altamente colaborativos. Esquemas de offloading que maximizan el tiempo de vida del ensemble de dispositivos.
- **Métricas clave:** Balanceo de energía entre nodos MDC para prolongar lifetime del ensemble de dispositivos.

## 8. Renee: New Life for Old Phones
- **Autores:** Jennifer Switzer, Eric Siu, Subhash Ramesh, Ruohan Hu, Emanoel Zadorian, Ryan Kastner (UC San Diego)
- **Año:** 2022
- **Conferencia/Repositorio:** UC San Diego ESL 2022
- **URL/DOI:** https://kastner.ucsd.edu/wp-content/uploads/2022/05/admin/esl22-Renee.pdf
- **Enfoque:** Clúster de smartphones usados con Function-as-a-Service (FaaS). Reemplazan Android por Ubuntu Touch. Nodo de gestión central (Raspberry Pi) como único punto de entrada.
- **Métricas clave:** Job `fib`: 1.5–1.9× más rápido que AWS Lambda. Overhead de gestión de clúster: 0.44–0.76 s adicionales.

## 9. Towards Green Computing: A Survey of Performance and Energy Efficiency of Different Platforms using OpenCL
- **Autores:** Philip Heinisch, Katharina Ostaszewski, Hendrik Ranocha
- **Año:** 2020
- **Conferencia:** arXiv preprint (cs.PF); publicado en ACM (dl.acm.org/doi/10.1145/3388333.3403035)
- **URL/DOI:** https://arxiv.org/html/2003.03794v1
- **Enfoque:** Compara time-to-solution y energy-to-solution en 22 GPUs discretas, 3 GPUs integradas, 14 CPUs de servidor/workstation y 4 CPUs ARM + 2 GPUs ARM integradas, usando OpenCL.
- **Métricas clave:** Energy-to-solution; time-to-solution. Dispositivos ARM: energía comparable o inferior a CPUs x86 modernos. GPU Mali G52 (2017) comparable en eficiencia a GPUs modernas en punto flotante de simple precisión.

## 10. Mobile Cloud for Parallel and Distributed Green Computing
- **Autores:** Leszek Siwik, Dawid Kala, Mateusz Godzik, Wojciech Turek, Aleksander Byrski, Marek Kisiel-Dorohinicki (AGH University of Krakow)
- **Año:** 2017
- **Conferencia/Revista:** Journal of Telecommunications and Information Technology (JTIT)
- **URL/DOI:** https://www.jtit.pl/jtit/article/view/690
- **Enfoque:** Mobile Cloud como sistema paralelo y distribuido de dispositivos móviles interconectados y virtualizados presentados como un recurso unificado. Construyen un clúster real de smartphones desfasados/abandonados.
- **Métricas clave:** Escalabilidad y eficiencia del clúster físico vs. conjunto virtualizado.

---

## Cómo se vinculan con tu caso de estudio (OpenCode Fleet)
- **Junkyard Computing / Renee:** demuestran que teléfonos usados + Linux (Ubuntu Touch) + Docker Swarm / FaaS son un clúster ARM real. Tu OpenCode Fleet (Termux + proot-distro + `opencode serve`) sigue la misma línea: Linux en espacio de usuario sin root sobre Android.
- **DroidCluster:** primer clúster empírico de smartphones (6 nodos, WiFi, LINPACK). Tu red MikroTik + Tailscale es la evolución de esa interconexión inalámbrica.
- **Scalable Smartphone Cluster / More is Different:** muestran el techo de desempeño con red cableada (Ethernet) vs. inalámbrica. Justifica por qué tu red segmentada con MikroTik es relevante.
- **Ou et al. / Heinisch et al.:** marcan la métrica FLOPS/Watt y energy-to-solution como estándar para comparar ARM vs x86. Usables para tu Big Message.
- **Mtibaa et al. / arXiv MPTCP:** MDC y múltiples interfaces de radio. Tu red híbrida (Wi-Fi + datos móviles + Tailscale) es directamente comparable.

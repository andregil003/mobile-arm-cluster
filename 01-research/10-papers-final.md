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
- **Relevancia para tu caso:** Teléfonos usados + Ubuntu Touch + Docker Swarm = clúster ARM real. Es el caso más directo de "granja de celulares como clúster".

---

## 2. DroidCluster: Towards Smartphone Cluster Computing — The Streets are Paved with Potential Computer Clusters
- **Autores:** Felix Büsching, Sebastian Schildt, Lars C. Wolf (TU Braunschweig, Alemania)
- **Año:** 2012
- **Conferencia:** 2012 32nd International Conference on Distributed Computing Systems Workshops (ICDCSW), pp. 114–117 (IEEE)
- **URL/DOI:** DOI: 10.1109/ICDCSW.2012.59 ; PDF: https://www.ibr.cs.tu-bs.de/papers/buesching-icdcs2012.pdf
- **Enfoque:** Clúster de seis teléfonos Android ejecutando MPI sobre WiFi. Benchmark LINPACK. Concluye que montar un clúster de smartphones es posible y razonable.
- **Métricas clave:** Seis teléfonos Android (LG P500, ARM11 600 MHz). Interconexión solo WiFi (punto de acceso permite teóricamente hasta 1024 nodos). LINPACK sobre WiFi.
- **Relevancia para tu caso:** Primer clúster empírico de smartphones. Tu red MikroTik + Tailscale es la evolución de esa interconexión inalámbrica entre nodos móviles.

---

## 3. Scalable Smartphone Cluster for Deep Learning
- **Autores:** Byunggook Na, Jaehee Jang, Seongsik Park, Seijoon Kim, Joonoo Kim, Moon Sik Jeong, Kwang Choon Kim, Seon Hee, Yoonsang Kim, Sungroh Yoon
- **Año:** 2021
- **Conferencia:** arXiv preprint (cs.LG / cs.DC)
- **URL/DOI:** https://arxiv.org/abs/2110.12172 (DOI: 10.48550/arXiv.2110.12172)
- **Enfoque:** Cluster de smartphones escalable para entrenamiento de DNN, conectando 138 dispositivos Galaxy S10+ mediante red cableada Ethernet. Entrenamiento síncrono de gran lote con Caffe.
- **Métricas clave:** 138 dispositivos Galaxy S10+ interconectados por Ethernet cableado; 90% de la velocidad de una GPU NVIDIA P100 en ResNet-50; ~43x speed-up sobre una GPU NVIDIA V100 en MobileNet-v1; límite inalámbrico ~30 smartphones.
- **Relevancia para tu caso:** Demuestra que la red cableada es clave para escalar; tu red MikroTik segmentada es análoga.

---

## 4. More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs
- **Autores:** Investigación de SoC Cluster como servidor de borde
- **Año:** 2024-07-17 (subida original 2022-12)
- **Conferencia:** arXiv preprint
- **URL/DOI:** https://arxiv.org/html/2212.12842
- **Enfoque:** Nuevo tipo de servidor de borde llamado **SoC Cluster**, que orquesta múltiples SoCs móviles de bajo consumo. Prototipo de 60 Qualcomm Snapdragon 865 en un rack 2U, desplegado en clouds de borde (cloud gaming).
- **Métricas clave:** Hasta 6.5× más throughput por unidad de energía para inferencia DL vs servidor con NVIDIA A40; comparable a NVIDIA A100. ResNet-50 quantizado: 8.8 ms de latencia de inferencia por SoC. SoC GPUs: ≈18 fps/J en ResNet-50 (FP32).
- **Relevancia para tu caso:** Validación comercial de clústeres ARM móviles para edge; métrica FLOPS/Watt clave.

---

## 5. Reinforcing Edge Computing with Multipath TCP Enabled Mobile Device Clouds
- **Autores:** propuesta de Mobile Device Cloud (MDC) con MPTCP
- **Año:** 2019-09-12 (v2)
- **Conferencia:** arXiv preprint
- **URL/DOI:** https://arxiv.org/html/1909.05530v2
- **Enfoque:** Mobile Device Cloud (MDC) habilitado con Multi-Path TCP (MPTCP). Aprovecha múltiples interfaces de radio (celular, Wi-Fi, Bluetooth) para aumentar el throughput y garantizar conectividad robusta.
- **Métricas clave:** Más de 63% de mejora en requests servidos con congestion handler vs sin él. Reducción de dropped requests a un nivel bajo y constante.
- **Relevancia para tu caso:** Tu red híbrida (Wi-Fi + datos móviles + Tailscale) es directamente comparable.

---

## 6. Renee: New Life for Old Phones
- **Autores:** Jennifer Switzer, Eric Siu, Subhash Ramesh, Ruohan Hu, Emanoel Zadorian, Ryan Kastner (UC San Diego)
- **Año:** 2022
- **Conferencia/Repositorio:** UC San Diego ESL 2022
- **URL/DOI:** https://kastner.ucsd.edu/wp-content/uploads/2022/05/admin/esl22-Renee.pdf
- **Enfoque:** Clúster de smartphones usados con Function-as-a-Service (FaaS). Reemplazan Android por Ubuntu Touch. Nodo de gestión central (Raspberry Pi) como único punto de entrada.
- **Métricas clave:** Job `fib`: 1.5–1.9× más rápido que AWS Lambda. Overhead de gestión de clúster: 0.44–0.76 s adicionales.
- **Relevancia para tu caso:** Tu OpenCode Fleet (Termux + proot-distro + `opencode serve`) sigue la misma línea: Linux sin root sobre Android, con gestión central.

---

## 7. Exploring Smartphone-Based Edge AI Inferences Using Real Testbeds
- **Autores:** Matías Hirsch, Cristian Mateos, Tim A. Majchrzak
- **Año:** 2025
- **Conferencia/Revista:** Sensors (MDPI), vol. 25, art. 2875
- **URL/DOI:** https://doi.org/10.3390/s25092875 ; PMC (texto completo): https://pmc.ncbi.nlm.nih.gov/articles/PMC12074420/
- **Enfoque:** Evalúa si un clúster de smartphones es competitivo para inferencia de visión por computadora en tiempo real frente a SBC. Tres modelos DL pre-tranados y ocho nodos heterogéneos (cinco smartphones + tres SBCs).
- **Métricas clave:** Clúster de 2-4 smartphones con Pull-Based ofrece rendimiento competitivo a un SBC x86 con ~3× menos energía. Clúster Cl409 (2 smartphones): ~1510 J vs Gigabyte Brix 4524 J en escenario BCS.
- **Relevancia para tu caso:** Es el paper más cercano al tema (reutilizar celulares como clúster ARM); demuestra empíricamente que clústeres de teléfonos usados compiten con SBC x86 consumiendo ~3× menos energía.

---

## 8. LinguaLinked: Distributed Large Language Model Inference on Mobile Devices
- **Autores:** Jie Zhao, Yizhou Song, Ian Harris, Sneha Abdu Jyothi
- **Año:** 2024
- **Conferencia:** 62nd Annual Meeting of the ACL (Volume 3: System Demonstrations), pp. 160–171
- **URL/DOI:** https://doi.org/10.18653/v1/2024.acl-demos.16 ; arXiv: 2312.00388
- **Enfoque:** Sistema descentralizado de inferencia distribuida de LLMs en dispositivos móviles. Segmenta el modelo y usa optimización lineal para asignar segmentos a cada dispositivo según su capacidad, con balanceador de carga en tiempo real. Ejecutado en CPU vía ONNX Runtime, sin GPU, manteniendo privacidad local.
- **Métricas clave:** 4 Android (3× Google Pixel 7 Pro, Tensor G2, 12 GB RAM; 1× CUBOT X30, Mediatek Helio P60, 8 GB RAM). BLOOM 1.1b/1.7b/3b. Aceleración de throughput 1.73×–2.65× (multihilo) vs línea base.
- **Relevancia para tu caso:** Es el paper más cercano a "agente/LLM en clúster de teléfonos" (LLMs distribuidos en Androids). Directo para tu OpenCode Fleet con `opencode serve`.

---

## 9. Prima.cpp: Fast 30-70B LLM Inference on Heterogeneous and Low-Resource Home Clusters
- **Autores:** Zonghang Li, Tao Li, Wenjiao Feng, Rongxing Xiao, Jianshu She, Hong Huang, Mohsen Guizani, Hongfang Yu, Qirong Ho, Wei Xiang, Xue Liu (MBZUAI / UESTC / CityU HK / La Trobe)
- **Año:** 2025 (arXiv: 2504.08791v3, 04 Jul 2026)
- **Conferencia:** arXiv cs.DC
- **URL/DOI:** https://arxiv.org/html/2504.08791 ; Código: https://github.com/OpenCPIL/prima.cpp
- **Enfoque:** Sistema de inferencia LLM distribuido en clústeres domésticos heterogéneos de bajo recurso. Incluye dispositivos móviles (Mate40Pro y Honor Pad mediante Termux en Android) dentro del clúster doméstico.
- **Métricas clave:** Dispositivos: Mac M1, laptop, desktop, Mate40Pro vía Termux + tablet Honor Pad; agregado RAM+VRAM 37 GiB. Llama 8B–70B (Q4K). 70B → 674 ms/token (TPOT) con <6 % presión de memoria; 32B con speculative decoding → 26 tokens/s. 5–17× menor TPOT y hasta 42× menor TTFT que llama.cpp / exo / dllama.
- **Relevancia para tu caso:** Incluye Android vía Termux en un clúster doméstico mixto — muy cercano a tu arquitectura OpenCode Fleet.

---

## 10. Towards Resource Sharing in Mobile Device Clouds: Power Balancing Across Mobile Devices
- **Autores:** Abderrahmen Mtibaa, Afnan Fahim, Khaled A. Harras, Mostafa H. Ammar (Texas A&M, Carnegie Mellon Qatar, Georgia Tech)
- **Año:** 2013
- **Conferencia:** SIGCOMM Mobile Cloud Computing (MCC) workshop 2013
- **URL/DOI:** https://conferences.sigcomm.org/sigcomm/2013/papers/mcc/p51.pdf
- **Enfoque:** Define Mobile Device Cloud (MDC) como offloading computacional realizado entre un conjunto de dispositivos móviles altamente colaborativos. Esquemas de offloading que maximizan el tiempo de vida del ensemble de dispositivos.
- **Métricas clave:** Balanceo de energía entre nodos MDC para prolongar lifetime del ensemble de dispositivos, bajo distintos supuestos de conectividad.
- **Relevancia para tu caso:** Tu arquitectura tiene nodos móviles con batería limitada; relevante para gestión de energía en tu granja de celulares.

---

## Cómo se vinculan con tu caso de estudio (OpenCode Fleet)
- **Junkyard / Renee:** demuestran que teléfonos usados + Linux (Ubuntu Touch) + Docker/FaaS son un clúster ARM real. Tu OpenCode Fleet sigue la misma línea: Linux en espacio de usuario sin root sobre Android.
- **DroidCluster:** primer clúster empírico de smartphones (6 nodos, WiFi, LINPACK). Tu red MikroTik + Tailscale es la evolución de esa interconexión.
- **Scalable Smartphone Cluster / More is Different:** muestran el techo de desempeño con red cableada (Ethernet) vs. inalámbrica. Justifica por qué tu red segmentada con MikroTik es relevante.
- **Hirsch et al. 2025 / LinguaLinked / Prima.cpp:** papers recientes (2024-2026) que validan directamente clústeres de smartphones para IA/LLM y edge computing, incluyendo uno con Android vía Termux (Prima.cpp).
- **Mtibaa et al.:** MDC y múltiples interfaces de radio. Tu red híbrida (Wi-Fi + datos móviles + Tailscale) es directamente comparable.

# LINKS VERIFICABLES — Investigación bibliográfica mobile-arm-cluster

Tema: Reutilización de granja de celulares para cluster ARM
Curso: Prácticas de Investigación 3 (Ing. Jorge Lara)
Fecha: 17 de noviembre de 2026

## PRIMERA TANDA — Papers fundamentales (10 papers)

### 1. Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon
- **Papel:** A1 — Más citado, caso directo de reutilización
- **Autores:** Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto (UC San Diego)
- **Año:** 2023
- **Conferencia:** ASPLOS '23 (ACM)
- **DOI:** https://doi.org/10.1145/3575693.3575710
- **arXiv:** https://arxiv.org/abs/2110.06870
- **PDF:** https://kastner.ucsd.edu/wp-content/uploads/2023/03/admin/asplos23-junkyard.pdf
- **Métrica clave:** 18.9× más eficiente en carbono vs AWS c5.9xlarge tras 3 años

### 2. DroidCluster: Towards Smartphone Cluster Computing
- **Papel:** A2 — Primer clúster empírico de smartphones
- **Autores:** Felix Büsching, Sebastian Schildt, Lars C. Wolf (TU Braunschweig)
- **Año:** 2012
- **Conferencia:** IEEE ICDCSW 2012
- **DOI:** https://doi.org/10.1109/ICDCSW.2012.59
- **IEEE Xplore:** https://ieeexplore.ieee.org/document/6258144
- **PDF (TU Braunschweig):** https://www.ibr.cs.tu-bs.de/papers/buesching-icdcs2012.pdf
- **Métrica clave:** 5.81 MFlops por nodo (LG P500, ARM11), 6 nodos WiFi

### 3. Energy- and Cost-Efficiency Analysis of ARM-Based Clusters
- **Papel:** A3 — Marco ARM vs x86 en MFLOPS/W
- **Autores:** Zhonghong Ou, B. Pang, Y. Deng, J. K. Nurminen, A. Ylä-Jääski, P. Hui (Aalto / HKUST)
- **Año:** 2012
- **Conferencia:** IEEE/ACM CCGrid 2012
- **DOI:** https://doi.org/10.1109/CCGRID.2012.84
- **IEEE Xplore:** https://ieeexplore.ieee.org/document/6217412
- **PDF (CiteSeerX):** https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1074.9789&rep=rep1&type=pdf
- **Métrica clave:** 2.6x–9.5x más eficiente que Intel; pico 1,046 MFLOPS/W

### 4. Scalable Smartphone Cluster for Deep Learning
- **Papel:** A4 — 138 Galaxy S10+ por Ethernet
- **Autores:** Byunggook Na, Jaehee Jang, Seongsik Park, Seijoon Kim, Joonoo Kim, Moon Sik Jeong, Kwang Choon Kim, Seon Hee, Yoonsang Kim, Sungroh Yoon
- **Año:** 2021
- **Fuente:** arXiv preprint (cs.LG / cs.DC)
- **arXiv:** https://arxiv.org/abs/2110.12172
- **DOI:** https://doi.org/10.48550/arXiv.2110.12172
- **Métrica clave:** 90% velocidad NVIDIA P100 (ResNet-50); 43× speed-up vs V100 (MobileNet-v1)

### 5. More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs
- **Papel:** A5 — SoC Cluster comercial
- **Autores:** Investigación de SoC Cluster
- **Año:** 2022/2024
- **Fuente:** arXiv preprint
- **arXiv:** https://arxiv.org/html/2212.12842
- **Métrica clave:** 60 Snapdragon 865; 6.5× throughput/W vs NVIDIA A40

### 6. Reinforcing Edge Computing with Multipath TCP Enabled Mobile Device Clouds
- **Papel:** A6 — MDC con MPTCP
- **Autores:** Investigación de MDC
- **Año:** 2019
- **Fuente:** arXiv preprint
- **arXiv:** https://arxiv.org/html/1909.05530v2
- **Métrica clave:** +63% requests servidos con congestion handler

### 7. Towards Resource Sharing in Mobile Device Clouds: Power Balancing Across Mobile Devices
- **Papel:** A7 — MDC y balanceo de energía
- **Autores:** Abderrahmen Mtibaa, Afnan Fahim, Khaled A. Harras, Mostafa H. Ammar
- **Año:** 2013
- **Conferencia:** SIGCOMM Mobile Cloud Computing (MCC) workshop 2013
- **PDF:** https://conferences.sigcomm.org/sigcomm/2013/papers/mcc/p51.pdf
- **Métrica clave:** Balanceo de energía para prolongar lifetime del ensemble

### 8. Renee: New Life for Old Phones
- **Papel:** A8 — FaaS en smartphones usados
- **Autores:** Jennifer Switzer, Eric Siu, Subhash Ramesh, Ruohan Hu, Emanoel Zadorian, Ryan Kastner (UC San Diego)
- **Año:** 2022
- **Fuente:** UC San Diego ESL 2022 (report)
- **PDF:** https://kastner.ucsd.edu/wp-content/uploads/2022/05/admin/esl22-Renee.pdf
- **Métrica clave:** 1.5–1.9× más rápido que AWS Lambda

### 9. Towards Green Computing: A Survey of Performance and Energy Efficiency using OpenCL
- **Papel:** A9 — Survey green computing ARM/x86
- **Autores:** Philip Heinisch, Katharina Ostaszewski, Hendrik Ranocha
- **Año:** 2020
- **Fuente:** arXiv preprint (cs.PF); publicado en ACM
- **arXiv:** https://arxiv.org/html/2003.03794v1
- **ACM DOI:** https://doi.org/10.1145/3388333.3403035
- **Métrica clave:** Energy-to-solution; ARM comparable o mejor que x86

### 10. Mobile Cloud for Parallel and Distributed Green Computing
- **Papel:** A10 — Clúster físico real de smartphones desfasados
- **Autores:** Leszek Siwik, Dawid Kala, Mateusz Godzik, Wojciech Turek, Aleksander Byrski, Marek Kisiel-Dorohinicki (AGH Krakow)
- **Año:** 2017
- **Revista:** Journal of Telecommunications and Information Technology (JTIT)
- **URL:** https://www.jtit.pl/jtit/article/view/690
- **Métrica clave:** Escalabilidad y eficiencia física vs virtualizada

---

## SEGUNDA TANDA — Papers recientes (2023-2026) + Proyectos reales

### A11. Exploring Smartphone-Based Edge AI Inferences Using Real Testbeds
- **Autores:** Matías Hirsch, Cristian Mateos, Tim A. Majchrzak
- **Año:** 2025
- **Revista:** Sensors (MDPI), vol. 25, art. 2875
- **DOI:** https://doi.org/10.3390/s25092875
- **PMC (texto completo):** https://pmc.ncbi.nlm.nih.gov/articles/PMC12074420/
- **PMID:** 40363312
- **Métrica clave:** ~3× menos energía que SBC x86 (Gigabyte Brix)

### A12. LinguaLinked: Distributed Large Language Model Inference on Mobile Devices
- **Autores:** Jie Zhao, Yizhou Song, Ian Harris, Sneha Abdu Jyothi
- **Año:** 2024
- **Conferencia:** 62nd Annual Meeting of the ACL (Volume 3: System Demonstrations), pp. 160–171
- **DOI:** https://doi.org/10.18653/v1/2024.acl-demos.16
- **arXiv:** https://arxiv.org/abs/2312.00388
- **Métrica clave:** 1.73×–2.65× speed-up multihilo en 4 Androids con BLOOM

### A13. Memory-Efficient Partitioned DNN Inference on Resource-Constrained Android Crowds (CROWDio subsistema)
- **Autores:** Lakshani Manamperi, Thiwanka Pathirana, Disumi Pathirana, Nipun Premarathna, Kutila Gunasekera (Univ. de Moratuwa)
- **Año:** 2026 (arXiv: 2605.20723v1, 20 May 2026)
- **Fuente:** arXiv cs.LG
- **arXiv:** https://arxiv.org/html/2605.20723v1
- **Métrica clave:** 43 ± 2 MB RSS por dispositivo; −34% latencia con streaming

### A14. FlexSpark: Robust and Efficient Multi-Device Collaborative Inference over Wireless Network
- **Autores:** Yiyang Shao, Hongyi Li, Shuihai Hu, Xinle Du, Hao Wu, Jingbin Zhou, Kun Tan (Huawei)
- **Año:** 2025
- **Conferencia:** APNet 2025, ACM
- **DOI:** https://doi.org/10.1145/3735358.3735368
- **ACM:** https://dl.acm.org/doi/full/10.1145/3735358.3735368
- **Métrica clave:** TTFT −51% vs single-device

### A15. Prima.cpp: Fast 30-70B LLM Inference on Heterogeneous and Low-Resource Home Clusters
- **Autores:** Zonghang Li, Tao Li, Wenjiao Feng, Rongxing Xiao, Jianshu She, Hong Huang, Mohsen Guizani, Hongfang Yu, Qirong Ho, Wei Xiang, Xue Liu (MBZUAI / UESTC / CityU HK / La Trobe)
- **Año:** 2025 (arXiv: 2504.08791v3, 04 Jul 2026)
- **Fuente:** arXiv cs.DC
- **arXiv:** https://arxiv.org/html/2504.08791
- **Código:** https://github.com/OpenCPIL/prima.cpp
- **Métrica clave:** Incluye Android vía Termux; 5–17× menor TPOT que llama.cpp

### A16. Evaluation of mobile ARM-based SoCs for high performance computing
- **Autores:** Investigación de conferencia (SpringSim 2016)
- **Año:** 2016
- **Conferencia:** SpringSim 2016 — HPC track
- **DOI:** https://doi.org/10.22360/SpringSim.2016.HPC.022
- **PDF:** https://dl.acm.org/doi/pdf/10.22360/SpringSim.2016.HPC.022
- **Métrica clave:** FLOPS/Watt como métrica central

### A17. Making the case for computational offloading in mobile device clouds
- **Autores:** Afnan Fahim, Abderrahmen Mtibaa, Khaled A. Harras
- **Año:** 2013
- **Conferencia:** MobiCom 2013, ACM
- **DOI:** https://doi.org/10.1145/2500423.2504576
- **ACM:** https://dl.acm.org/doi/10.1145/2500423.2504576
- **Informe técnico CMU:** http://ra.adm.cs.cmu.edu/cs2013.html

### A18. Junkyard Computing (ASPLOS 2023 — duplicado confirmado)
- **Ver entrada A1 arriba.**

### A19. Distributed Inference of Large Language Models on Edge Devices (ICSCA 2025)
- **Autores:** Karthik Namboori, Rohit P Suresh, Sathwik Hj, Shriansh Mohanty, Jayashree Rangareddy (PES University)
- **Año:** 2025
- **Conferencia:** ICSCA '25, ACM
- **DOI:** https://doi.org/10.1145/3731806.3731859
- **ACM:** https://dl.acm.org/doi/10.1145/3731806.3731859
- **Métrica clave:** Hasta 74% mejora en tiempo de inferencia por token con 4 nodos Termux

### A20. Supporting Sustainable Computing by Repurposing E-Waste Smartphones as Tiny Data Centers
- **Autores:** Perseverance Ngoy, Farooq Dar, Mohan Liyanage, et al. (Univ. de Tartu, Helsinki, FH Dortmund, Madeira)
- **Año:** 2025
- **Revista:** IEEE Pervasive Computing, vol. 24, pp. 53–60
- **DOI:** https://doi.org/10.1109/MPRV.2025.3541558
- **IEEE:** https://www.computer.org/csdl/magazine/pc/2025/01/10925535/253t8JZhgYg
- **Métrica clave:** 4 teléfonos Nexus, rack impreso en 3D, postmarketOS, costo < $10

### A21. SimDC: A High-Fidelity Device Simulation Platform for Device-Cloud Collaborative Computing
- **Autores:** Investigación de arXiv
- **Año:** 2025
- **Fuente:** arXiv preprint
- **arXiv:** https://arxiv.org/html/2503.22288v2

### A22. Zombitron: towards a toolbox for repurposing obsolete smartphones into new interactive systems
- **Autores:** Clara Rigaud
- **Año:** 2025
- **Fuente:** arXiv preprint / LIMITS '25
- **arXiv:** https://arxiv.org/html/2508.06354v1

### A23. An easy way to boost home calculation performance with HGRID
- **Autores:** Sergey A. Balabaev, Sergey Lupin
- **Año:** 2026
- **Revista:** International Journal of Open Information Technologies, vol. 14, no. 5
- **URL:** http://injoit.org/index.php/j1/article/view/2573/0

### A24. Monitoring system for load balancing of distributed computing system nodes based on smartphones
- **Autores:** Sergey Balabaev, Sergey Lupin, Aye Min Thike
- **Año:** 2024
- **Revista:** IJOIT vol. 12, no. 10
- **URL:** http://injoit.org/index.php/j1/article/view/1928/0

### A25. Low-cost edge computing using upcycled smartphones
- **Autores:** Corentin Libert
- **Año:** 2024
- **Institución:** Ecole polytechnique de Louvain (UCLouvain) — tesis de máster
- **URL:** http://dial-mem.test.bib.ucl.ac.be/handle/2078.2/42370

### A26. Konzeption und Implementierung eines Mobiltelefon-Clusters...
- **Autores:** Lukas Greifeneder
- **Año:** 2025
- **Institución:** Masterarbeit, Hochschule Burgenland (alemán)
- **PDF:** https://cloud-day.hochschule-burgenland.at/2026/wp-content/uploads/sites/4/2026/05/MA_2310781016_Greifeneder_Lukas.pdf

### A27. About one Approach to Organizing a Home Distributed Computing System
- **Autores:** Sergey Balabaev, Sergey Lupin, Dmitry Fedyashin
- **Año:** 2025
- **Revista:** IJOIT
- **URL:** http://injoit.org/index.php/j1/article/view/2312

### A28. Reuse of Retired Mobile Devices in Cyber-Physical Systems
- **Autores:** Timothy Ambrose (asesor: Rajeevan Amirtharajah)
- **Año:** 2023
- **Institución:** UC Davis eScholarship — tesis doctoral
- **URL:** https://escholarship.org/uc/item/8cp0h66g

### A29. More is Different (USENIX ATC 2024 — duplicado confirmado)
- **Ver entrada A5 arriba.**

### A30. Opportunities and Challenges in Securely Reusing and Repurposing Mobile Devices
- **Autores:** Adelin Roty, Jan Tobias Mühlberg, Jean-François Determe (ULB, Bruselas)
- **Año:** 2026 (arXiv: 2606.06181, 05 Jun 2026)
- **Fuente:** arXiv preprint / 12th Workshop on Computing within Limits
- **arXiv:** https://arxiv.org/html/2606.06181
- **Métrica clave:** 5.300 millones de teléfonos como e-waste en 2022; vida media ~3 años

### A31. A Comparative Analysis of ARM and x86-64 Laptop-Class Processors
- **Autores:** Mustafa Mert Özyılmaz
- **Año:** 2026 (arXiv: 2604.18896v1, 20 Abr 2026)
- **Fuente:** arXiv cs.AR
- **arXiv:** https://arxiv.org/abs/2604.18896v1
- **arXiv (HTML):** https://arxiv.org/html/2604.18896v1
- **Métrica clave:** Apple M3 vs Ryzen 7 3750H; 5.82× (Fib) y 6.38× (matmul) energy-to-solution

### A32. Energy Concerns with HPC Systems and Applications
- **Autores:** Roblex T. Nana, Claude Tadonki, Petr Dokladal, Youssef Mesri
- **Año:** 2023 (arXiv v2, 17 Feb 2026)
- **Fuente:** arXiv cs.CY
- **arXiv:** https://arxiv.org/abs/2309.08615v2
- **arXiv (HTML):** https://arxiv.org/html/2309.08615v2
- **Métrica clave:** FLOPS/Watt (Green500); supercómputo hasta 29.9 MW

### A33. Redefining Computing: Rise of ARM from consumer to Cloud
- **Autores:** Tahmid Noor Rahman, Nusaiba Khan, Zarif Ishmam Zaman
- **Año:** 2024 (arXiv: 2402.02527, 4 Feb 2024)
- **Fuente:** arXiv cs.CE
- **arXiv:** https://arxiv.org/abs/2402.02527
- **DOI relacionado:** https://doi.org/10.30574/wjarr.2024.21.1.0017
- **Métrica clave:** Marco cualitativo ARM vs x86 (no cifras numéricas)

### A34. A Methodology to Assess Power Modeling in Energy-Aware Federated Learning
- **Autores:** Chaimae Jallouli, Karim Boubouh, Robert Basmadjian
- **Año:** 2026 (arXiv: 2605.27601v1, 26 May 2026)
- **Fuente:** arXiv cs.DC; aceptado en NETYS 2026
- **arXiv:** https://arxiv.org/abs/2605.27601v1
- **arXiv (HTML):** https://arxiv.org/html/2605.27601v1
- **Métrica clave:** Error modelo CMOS <10%; 1.4× menos energía con modelo analítico

### A35. Characterizing and Understanding Energy Footprint of Small Language Model on Edges
- **Autores:** Md Romyull Islam, Bobin Deng, Nobel Dhar, Tu N. Nguyen, Selena He, Yong Shi, Kun Suo
- **Año:** 2025 (arXiv: 2511.11624v1, 7 Nov 2025)
- **Fuente:** arXiv cs.DC; presentado en IEEE MASS 2025
- **arXiv:** https://arxiv.org/abs/2511.11624
- **arXiv (HTML):** https://arxiv.org/html/2511.11624v1
- **Métrica clave:** TPWh, EDP, energía por inferencia en Pi 5 / Jetson

### A36. Design and Implementation of an IoT Cluster with Raspberry Pi Powered by Solar Energy
- **Autores:** Noel Portillo
- **Año:** 2025 (arXiv: 2503.03618, 5 Mar 2025)
- **Fuente:** arXiv cs.DC; publicado previamente en Zenodo
- **arXiv:** https://arxiv.org/abs/2503.03618
- **Zenodo:** https://doi.org/10.5281/zenodo.14957338
- **Métrica clave:** Panel solar 200 W + batería 100 Ah; clúster RPi 3 con K3s

### A37. Experimenting with Energy-Awareness in Edge-Cloud Containerized Application Orchestration
- **Autores:** Dalal Ali, Rute C. Sofia
- **Año:** 2025 (arXiv: 2511.09116v1, 12 Nov 2025)
- **Fuente:** arXiv cs.NI
- **arXiv:** https://arxiv.org/abs/2511.09116
- **arXiv (HTML):** https://arxiv.org/html/2511.09116v1
- **Métrica clave:** Orquestación consciente de energía en clústeres ARM de borde

### A38. WiCi: Wireless GPU Computing Infrastructure
- **Autores:** Yibin Shen, Wei Li, Kaiqiang Xu, Zili Meng
- **Año:** 2026 (arXiv: 2608.24204v1, 25 Aug 2026)
- **Fuente:** arXiv cs.NI
- **arXiv:** https://arxiv.org/html/2608.24204v1
- **Métrica clave:** TTFT reducido hasta 90%; token rate ~39× superior a móvil local

---

## B. ANUNCIOS CORPORATIVOS E INSTITUCIONALES

### B1. A low-carbon computing platform from your retired phones
- **Autor:** Google Research + UC San Diego
- **Fecha:** 2026-06-12
- **URL:** https://research.google/blog/a-low-carbon-computing-platform-from-your-retired-phones/
- **Métrica clave:** 2.000 teléfonos Pixel; 25–50 teléfonos ≈ 1 servidor; clúster de 20 teléfonos soportó clase de 75+ estudiantes

### B2. Arm C1 CPU cluster / Armv9 CPUs
- **Autor:** Arm Newsroom
- **Fechas:** 2025-09-10 / 2024-05-29
- **URL:** https://newsroom.arm.com/blog/arm-c1-cpu-cluster-on-device-ai-performance

---

## C. PROYECTOS REALES (GitHub / Comunidad / Blogs)

### C1. PhoneBorg — dzaczek
- **URL:** https://github.com/dzaczek/phoneborg
- **Año:** 2026 (activo, 193 commits)
- **Dispositivos:** 5 teléfonos (Pixel 8 Pro, OnePlus 10 Pro, POCO F3, Xiaomi Mi 8, Xiaomi MI 9)
- **Arquitectura:** Controller Go + gateway OpenAI + failover/pools + Big Brain (llama.cpp RPC)
- **Métrica clave:** OnePlus 10 Pro: 29,0 / 13,3 / 4,6 / 2,9 tok/s para 0,5B/1,5B/4B/8B (Q4_K_M)

### C2. Phonon — chezgoulet
- **URL:** https://github.com/chezgoulet/phonon
- **Año:** 2026 (v0.1.15)
- **Dispositivos:** 1 medido (Google Pixel 7)
- **Arquitectura:** LiteLLM gateway + opencode host; llama-server en teléfono
- **Métrica clave:** Pixel 7, Qwen3.5-2B Q4_K_M: 14,01 tok/s burst, 10,54 tok/s sostenido

### C3. android-ai-agent-cluster — Ishuin
- **URL:** https://github.com/Ishuin/android-ai-agent-cluster
- **Docs:** https://raw.githubusercontent.com/Ishuin/android-ai-agent-cluster/main/docs/agents.md
- **Dispositivos:** 2 (Redmi Note 8 Pro edge; Samsung A52 worker)
- **Arquitectura:** JSON/HTTP edge+worker sobre Termux; boot scripts Termux:Widget

### C4. termux/proot-distro
- **URL:** https://github.com/termux/proot-distro
- **Año:** publicado 2020-07-20; última release v5.10.3 (PyPI)
- **Arquitectura:** Contenedores Linux rootless en Termux (proot, sin root, sin Docker)
- **Relevancia:** Base técnica para correr Ubuntu/Debian + `opencode serve` en Android sin root

### C5. postmarketOS-powered Kubernetes cluster — Denys Vitali
- **URL:** https://blog.denv.it/posts/pmos-k3s-cluster/
- **Fecha:** 2024-11-25
- **Dispositivos:** 3 teléfonos (OnePlus 5T, OnePlus 8 Pro)
- **Arquitectura:** k3s v1.31.2 + postmarketOS; Wi-Fi ~200 Mbit/s

### C6. Hacker News — debate postmarketOS k3s
- **URL:** https://news.ycombinator.com/item?id=42352075
- **Fecha:** 2024-12-13

### C7. Hacker News — debate Google/UCSD 2.000 Pixels
- **URL:** https://news.ycombinator.com/item?id=48515336
- **Fecha:** julio 2026

### C8. Reddit — kubernetes cluster con Android phones viejos
- **URL:** https://www.reddit.com/r/homelab/comments/1ui5gan/i_created_a_kubernetes_cluster_using_old_android/
- **Fecha:** 2026

### C9. Reddit — project ideas cluster Android devices
- **URL:** https://www.reddit.com/r/hacking/comments/1au051o/project_ideas_for_a_cluster_of_android_devices/
- **Fecha:** 2024

### C10. Reddit — Home Server con Android
- **URL:** https://www.reddit.com/r/selfhosted/comments/1h7z9js/what_do_you_think_about_my_new_home_server/
- **Fecha:** 2024

### C11. appium-device-farm
- **URL:** https://github.com/AppiumTestDistribution/appium-device-farm
- **Estado:** Activo; último commit 2026-10-16
- **Métrica clave:** >126 tests pasando en release v12

### C12. TESAR-Live
- **URL:** https://github.com/mashfikuzzaman-2023415968-cell/TESAR-live
- **Estado:** Código abierto / GitHub (fecha no verificable exactamente)
- **Métrica clave:** >1.460 pruebas; políticas de scheduling (local, round_robin, fastest, most_reliable, tesar)

### C13. scrcpy-farm
- **URL:** https://github.com/beytgoal/scrcpy-farm
- **Fecha:** 2026-07-18
- **Métrica clave:** Hasta 100 dispositivos; 100 dispositivos eco @10 FPS ≈ 50 Mbps total

### C14. opencode-multi-agent-farm (adyacente, no nodos Android)
- **Autor:** AAliKKhan
- **URL:** https://github.com/AAliKKhan/opencode-multi-agent-farm
- **Nota:** Agentes en Windows PC; Android solo como consola remota (OpenCode Mobile + Tailscale)

---

## D. RECURSOS DEL CURSO (PI3 — Ing. Jorge Lara)

### D1. Programa del curso
- **Archivo:** `C:\Users\andre\Downloads\Practica de Investigaci�n 3 - Jorge Lara (2026).docx`
- **Entregable:** Paper review (estado del arte) formato IEEE, entrega Semana 4 (7–11 dic)
- **Bibliografía:** 10 papers para Semana 2 (23–27 nov)

### D2. Selección de Tema para Paper
- **Archivo:** `C:\Users\andre\Downloads\Selecci�n de Tema para Paper.pdf`
- **Texto extraído:** `C:\Users\andre\AppData\Local\Temp\opencode\Selecci�n de Tema para Paper.txt`
- **Tema elegido:** Reutilización de granja de celulares para cluster ARM

### D3. Writing Human Factors Research (bibliografía base del curso)
- **Archivo:** `C:\Users\andre\Downloads\Writing Human Factors Research - Don Harris (1).pdf`
- **Texto extraído:** `C:\Users\andre\AppData\Local\Temp\opencode\Writing Human Factors Research - Don Harris (1).txt`
- **Referencia:** Don Harris (2012), metodología para paper de investigación

### D4. IEEE-paper-format-template.docx
- **Archivo:** `C:\Users\andre\Downloads\IEEE-paper-format-template.docx`
- **Uso:** Template para el paper final del curso

### D5. Propuestas PI3 2026
- **Archivo:** `C:\Users\andre\Downloads\Propuestas PI3 2026.txt`
- **Contenido:** Temas asignados por estudiante; "Reutilización de granja de celulares para cluster ARM" aparece en línea 36 (áreas abiertas) y bajo nombre de Jorge André Gil Leonardo

---

## E. REPOSITORIO GITHUB

- **URL:** https://github.com/andregil003/mobile-arm-cluster
- **Usuario:** andregil003 (público)
- **Rama:** master (trackeando origin/master)
- **Último commit:** c9e014c — feat: segunda tanda de investigación bibliográfica
- **Ruta local:** C:\Users\andre\Documents\GitHub\mobile-arm-cluster

---

## NOTA DE HONESTIDAD METODOLÓGICA

Todos los links arriba son accesibles y verificables al momento de la consulta (17 de noviembre de 2026). Algunos repositorios GitHub no indican año de publicación explícito; en esos casos se declara "no indicado". Ningún paper, título, autor, métrica o URL fue inventado.

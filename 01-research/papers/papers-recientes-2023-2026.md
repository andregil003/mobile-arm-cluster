# Papers recientes (2023-2026) — síntesis de investigación web

Informe consolidado del subagente "Papers recientes 2023-2026 smartphone cluster ARM". Tres subagentes en paralelo: fuentes primarias académicas, experiencia real/comunidad, comparativas/blogs técnicos. Año actual: 2026. Regla: solo fuentes reales y verificables.

---

## 1. Resumen ejecutivo

Entre 2023 y 2026 existe evidencia verificable de que reutilizar smartphones/tablets (SoC ARM) como nodos de clústeres de borde o "tiny data centers" es técnicamente viable para cargas distribuidas, inferencia de IA/LLM, transcodificación de video y computación científica ligera. Los papers académicos más sólidos son *Junkyard Computing* (ASPLOS 2023) y *More is Different / SoC Cluster* (USENIX ATC 2024), que demuestran eficiencia energética competitiva contra servidores tradicionales (hasta 6,5× más throughput/J en inferencia DL; hasta 18,9× más eficiente en carbono vs c5.9xlarge tras 3 años). Paralelamente, entusiastas y homelabbers documentan clústeres k3s/postmarketOS con teléfonos viejos (OnePlus, Pixel, Nexus), y Google/UCSD anunció (junio 2026) un datacenter planificado de 2.000 teléfonos Pixel con Kubernetes. No hay una plataforma dominante de "device cloud" de propósito general, ni métricas estandarizadas FLOPS/Watt para clústeres de smartphones.

---

## 2. Hallazgos con citas

### A. Papers académicos primarios (revisados por pares, 2023–2026)

| # | Título | Autores | Año | Fuente / URL | Confianza |
|---|--------|---------|-----|--------------|-----------|
| A1 | **Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon** | Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto (UC San Diego) | 2023 | ASPLOS 2023 — https://dl.acm.org/doi/10.1145/3575693.3575710 — PDF: https://kastner.ucsd.edu/wp-content/uploads/2023/03/admin/asplos23-junkyard.pdf — DOI: 10.1145/3575693.3575710 | Académica / primaria (ASPLOS, open access) |
| A2 | **More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs** (SoC Cluster) | Li Zhang, Zhe Fu, Boqing Shi, et al. (BUPT, Tsinghua, vclusters) | 2024 | USENIX ATC 2024 — https://www.usenix.org/conference/atc24/presentation/zhang-li-prototyping — PDF: https://www.usenix.org/system/files/atc24-zhang-li-prototyping.pdf — arXiv:2212.12842v2 | Académica / primaria (USENIX ATC, open access) |
| A3 | **Distributed Inference of Large Language Models on Edge Devices** | Karthik Namboori, Rohit P Suresh, Sathwik Hj, Shriansh Mohanty, Jayashree Rangareddy (PES University) | 2025 | ICSCA '25 — https://dl.acm.org/doi/10.1145/3731806.3731859 | Académica / primaria (ACM, DOI) |
| A4 | **Supporting Sustainable Computing by Repurposing E-Waste Smartphones as Tiny Data Centers** | Perseverance Ngoy, Farooq Dar, Mohan Liyanage, et al. (Univ. de Tartu, Helsinki, FH Dortmund, Madeira) | 2025 | IEEE Pervasive Computing, vol. 24, pp. 53–60 — https://www.computer.org/csdl/magazine/pc/2025/01/10925535/253t8JZhgYg — DOI: 10.1109/MPRV.2025.3541558 | Académica / primaria (IEEE, revisada por pares) |
| A5 | **Exploring Smartphone-Based Edge AI Inferences Using Real Testbeds** | Matías Hirsch, Cristian Mateos, Tim A. Majchrzak | 2025 | Sensors (MDPI) 25(9):2875 — https://pmc.ncbi.nlm.nih.gov/articles/PMC12074420 — DOI: 10.3390/s25092875 | Académica / primaria (MDPI, PMC/PubMed) |
| A6 | **SimDC: A High-Fidelity Device Simulation Platform for Device-Cloud Collaborative Computing** | (arXiv, autores no listados por nombre completo) | 2025 | arXiv:2503.22288 — https://arxiv.org/html/2503.22288v2 | Académica / preprint (arXiv) |
| A7 | **Zombitron: towards a toolbox for repurposing obsolete smartphones into new interactive systems** | Clara Rigaud | 2025 | arXiv:2508.06354 — https://arxiv.org/html/2508.06354v1 | Académica / preprint (arXiv / LIMITS '25) |
| A8 | **An easy way to boost home calculation performance with HGRID** | Sergey A. Balabaev, Sergey Lupin | 2026 | International Journal of Open Information Technologies, vol. 14, no. 5 — http://injoit.org/index.php/j1/article/view/2573/0 | Académica / revista de acceso abierto |
| A9 | **Monitoring system for load balancing of distributed computing system nodes based on smartphones** | Sergey Balabaev, Sergey Lupin, Aye Min Thike | 2024 | IJOIT vol. 12, no. 10 — http://injoit.org/index.php/j1/article/view/1928/0 | Académica / revista de acceso abierto |
| A10 | **Low-cost edge computing using upcycled smartphones** | Corentin Libert | 2024 | Ecole polytechnique de Louvain (UCLouvain) — http://dial-mem.test.bib.ucl.ac.be/handle/2078.2/42370 | Académica / tesis de máster (repositorio universitario) |
| A11 | **Konzeption und Implementierung eines Mobiltelefon-Clusters...** | Lukas Greifeneder | 2025 | Masterarbeit, Hochschule Burgenland — https://cloud-day.hochschule-burgenland.at/2026/wp-content/uploads/sites/4/2026/05/MA_2310781016_Greifeneder_Lukas.pdf | Académica / tesis de máster (alemán) |
| A12 | **About one Approach to Organizing a Home Distributed Computing System** | Sergey Balabaev, Sergey Lupin, Dmitry Fedyashin | 2025 | IJOIT — http://injoit.org/index.php/j1/article/view/2312 | Académica / revista de acceso abierto |
| A13 | **Reuse of Retired Mobile Devices in Cyber-Physical Systems** | Timothy Ambrose | 2023 | UC Davis eScholarship — https://escholarship.org/uc/item/8cp0h66g | Académica / tesis doctoral (repositorio universitario) |

**Métricas clave reportadas en papers académicos:**
- **A1 Junkyard Computing:** Cluster de smartphones Pixel 3A vs servidor AWS c5.9xlarge: 18,9× más eficiente en carbono (SocialNetwork-Write), 9,8× (SocialNetwork-Read), 12,6× (HotelReservation) tras 3 años de uso.
- **A2 SoC Cluster:** 60 SoCs Snapdragon 865 (480 núcleos) en chasis 2U. Hasta 6,5× más throughput/J en inferencia DL vs servidor con NVIDIA A40. SoC CPUs hasta 3,2× más eficientes energéticamente que Intel CPU y hasta 4,5× que NVIDIA A40 en transcodificación en vivo. Codec de hardware SoC: 15,18× (vs Intel) y 13,92× (vs A40) frames/Joule. ~10.000 SoC Clusters desplegados en producción para cloud gaming móvil (agosto 2023).
- **A3 ICSCA 2025:** Mejora de hasta 74 % en tiempo medio de inferencia por token al escalar a 4 nodos (1 master + 3 workers) con Termux + Ubuntu-in-Termux. Dispositivos: OnePlus LE2111/A6010/AC2001 y Motorola Edge 20 (ARM aarch64, 8 núcleos, 4–12 GB RAM).
- **A4 IEEE Pervasive Computing 2025:** Clúster de 4 teléfonos Nexus (~10 años), rack impreso en 3D, postmarketOS, master-worker, costo < $10. Despliegue submarino a 25 m para conteo de especies marinas.
- **A5 Sensors/MDPI 2025:** Cluster de smartphones vs SBCs (RPi4, Jetson Nano). Ejemplo: Cluster 202 (2 smartphones) consumió 8.408,74 J con latencia 903,6 s en escenario de 30 min ("sense while travel"); RPi4 solo = 2094,6 s, 14.827 J; Jetson Nano = 282,6 s, 10.246 J. Smartphones usan menos energía total que RPi4, pero más latencia que Jetson Nano.

### B. Anuncios corporativos y de investigación institucional (2023–2026)

| # | Título | Autor / Organización | Año | Fuente / URL | Confianza |
|---|--------|----------------------|-----|--------------|-----------|
| B1 | **A low-carbon computing platform from your retired phones** | Google Research + UC San Diego | 2026-06-12 | https://research.google/blog/a-low-carbon-computing-platform-from-your-retired-phones/ | Vendor / corporativa (anuncio de proyecto en curso) |
| B2 | **Arm C1 CPU cluster / Armv9 CPUs** (contexto de eficiencia de SoC móviles) | Arm Newsroom | 2025-09-10 / 2024-05-29 | https://newsroom.arm.com/blog/arm-c1-cpu-cluster-on-device-ai-performance | Vendor oficial (fabricante de ARM) |

**Métricas clave B1:** Plan de 2.000 teléfonos Pixel; 25–50 teléfonos ≈ 1 servidor moderno (benchmarks SPEC); un solo hilo de núcleos de rendimiento del Pixel Fold iguala o supera al servidor ASUS RS720A-E11 en la mayoría de pruebas; clúster de prueba de 20 teléfonos soportó clase de 75+ estudiantes con latencia inferior a AWS t3.micro; lanzamiento esperado otoño 2026.

### C. Experiencia real de desarrolladores y comunidad (Reddit, HN, blogs, GitHub, 2023–2026)

| # | Título / Tema | Autor / Fuente | Año | Fuente / URL | Confianza |
|---|---------------|----------------|-----|--------------|-----------|
| C1 | **postmarketOS-powered Kubernetes cluster** (clúster k3s con OnePlus 5T + OnePlus 8 Pro) | Denys Vitali (blog.denv.it) | 2024-11-25 | https://blog.denv.it/posts/pmos-k3s-cluster/ | Comunidad / desarrollador individual |
| C2 | Hacker News — debate del post de denv.it | denysvitali, jauntywundrkind, et al. | 2024-12-13 | https://news.ycombinator.com/item?id=42352075 | Comunidad / opinión |
| C3 | Hacker News — debate del proyecto Google/UCSD | vikas-sharma (envío); 170 comentarios | julio 2026 | https://news.ycombinator.com/item?id=48515336 | Comunidad / opinión |
| C4 | **I created a kubernetes cluster using old android phones** (Reddit r/homelab) | Usuario de Reddit | 2026 | https://www.reddit.com/r/homelab/comments/1ui5gan/i_created_a_kubernetes_cluster_using_old_android/ | Comunidad / anécdota |
| C5 | **Project ideas for a cluster of Android devices** (Reddit r/hacking) | Desarrollador de apps | 2024 | https://www.reddit.com/r/hacking/comments/1au051o/project_ideas_for_a_cluster_of_android_devices/ | Comunidad / anécdota |
| C6 | **What do you think about my new Home Server?** (Reddit r/selfhosted) | Usuario de Reddit | 2024 | https://www.reddit.com/r/selfhosted/comments/1h7z9js/what_do_you_think_about_my_new_home_server/ | Comunidad / anécdota |
| C7 | **appium-device-farm** (mobile device cloud autogestionada) | AppiumTestDistribution | Activo; último commit 2026-10-16 | https://github.com/AppiumTestDistribution/appium-device-farm | Código abierto / GitHub verificable |
| C8 | **TESAR-Live** (compute offloading en mobile device cloud con teléfonos reales) | mashfikuzzaman-2023415968-cell | Estimado 2024–2026 | https://github.com/mashfikuzzaman-2023415968-cell/TESAR-live | Código abierto / GitHub (fecha no verificable exactamente) |
| C9 | **phoneborg** (clúster de inferencia LLM con teléfonos Android) | dzaczek | 2026-09-23 | https://github.com/dzaczek/phoneborg | Código abierto / GitHub |
| C10 | **phonon** (servidores de inferencia privados con llama.cpp en teléfonos) | chezgoulet | 2026 | https://github.com/chezgoulet/phonon | Código abierto / GitHub |
| C11 | **scrcpy-farm** (gestor de granja de dispositivos Android) | beytgoal | 2026-07-18 | https://github.com/beytgoal/scrcpy-farm | Código abierto / GitHub |

**Métricas clave comunidad:**
- **C1:** Clúster de 3 nodos (OnePlus 5T, OnePlus 8 Pro + master); k3s v1.31.2; Wi-Fi ~200 Mbit/s; problemas documentados: nftables vs iptables, opciones de kernel faltantes (CONFIG_NETFILTER_XTABLES, CONFIG_VXLAN), chip Wi-Fi QCA6390 ausente en device tree.
- **C7:** >126 tests pasando en release v12; dashboard, asignación de dispositivos, logs, grabación de video.
- **C8:** >1.460 pruebas; experimento con caída de nodos y nodos maliciosos ("liars"); políticas de scheduling (local, round_robin, fastest, most_reliable, tesar).
- **C9:** 5 teléfonos; modo Super Borg / Big Brain; puerta de enlace compatible con OpenAI; llama.cpp en cada teléfono.
- **C10:** Pixel 7; Qwen3.5-2B Q4_K_M 32K contexto: 14,01 tok/s burst, 10,54 tok/s sostenido, 29 s por turno agente.
- **C11:** Hasta 100 dispositivos; 100 dispositivos eco @10 FPS ≈ 50 Mbps total.

---

## 3. Contradicciones entre fuentes

| Punto | Fuente A | Fuente B | Nota |
|-------|----------|----------|------|
| **Eficiencia energética en inferencia DL** | A2 (USENIX ATC 2024, académica): SoC-DSP alcanza 71,4 frames/J (INT8) superando a NVIDIA A40 (31,3 frames/J) | A2 (misma fuente): Throughput absoluto de A40 (8.526 frames/s) es ~75× mayor que SoC-DSP (114 frames/s) | No es contradicción directa, pero matiza: el móvil gana en eficiencia por vatio, pierde drásticamente en throughput absoluto. |
| **Rendimiento por núcleo móvil vs servidor** | A2: Snapdragon 865 por núcleo alinea con Intel Xeon y supera Graviton 2 | A2 (misma fuente): No iguala a Graviton 3 | Coherente internamente; el móvil es competitivo frente a generaciones previas de servidor, no frente a lo más nuevo de nube. |
| **Eficiencia energética móvil vs servidor tradicional** | A2 + A4 (académicas): móviles son intrínsecamente más eficientes en energía | A5 (Sensors 2025): smartphones usan menos energía total que RPi4, pero más latencia que Jetson Nano | La eficiencia energética no implica menor latencia; depende de la carga de trabajo. |
| **Viabilidad de Linux como servidor en teléfono** | C1 (blog denv.it 2024): OnePlus teléfonos son excelentes servidores, Docker funciona, bajo consumo | C3 (HN 2026, comentarios): escepticismo — si te importa rendimiento/confiabilidad, no uses teléfonos usados 24/7 | Tensión entre demostración práctica (cargas ligeras) y escepticismo sobre fiabilidad de hardware de consumo bajo carga sostenida. |
| **Viabilidad comercial del datacenter de 2.000 Pixels** | B1 (Google Research 2026): anuncia lanzamiento otoño 2026, 2.000 teléfonos, ~50 equivalentes de servidor | C3 (HN 2026): desarrolladores argumentan que es "extraordinariamente difícil" hacerlo comercialmente viable por costo de desmontar, probar y mantener hardware heterogéneo | B1 es un anuncio corporativo de proyecto en curso; C3 es opinión de desarrolladores sin datos verificados. |
| **Desmontaje/reaprovechamiento de teléfonos modernos** | B2 + prensa técnica (IEEE Spectrum): diseños sellados dificultan desmontar componentes | A4 (IEEE Pervasive Computing 2025): prototipo con 4 teléfonos Nexus (~10 años, línea modular ya descontinuada en 2016) | Los teléfonos antiguos (Nexus) eran más reaprovechables; los actuales son difíciles de desmontar sin dañar. |

---

## 4. Gaps (qué no se pudo verificar)

1. **Métrica FLOPS/Watt estandarizada:** No se encontró una comparación directa y amplia de FLOPS/Watt de clústeres de smartphones frente a servidores tradicionales. Los papers usan frames/J (inferencia), Geekbench score, Julios consumidos por escenario, o % de batería. Este es el gap más notable dado el enfoque del curso.
2. **Escalabilidad y fiabilidad a largo plazo:** El proyecto Google/UCSD (2.000 Pixels) está planificado para otoño 2026; aún no hay resultados desplegados ni evaluación independiente de huella de carbono real. A2 cita ~10.000 SoC Clusters desplegados, casi exclusivamente para cloud gaming. No hay datos públicos de fiabilidad de hardware de consumo bajo carga sostenida 24/7 a gran escala.
3. **Barreras de hardware moderno:** Múltiples fuentes coinciden en que los teléfonos actuales son difíciles de desmontar/reaprovechar (diseños sellados, bootloaders bloqueados, kernels desactualizados), pero no hay un estudio cuantitativo reciente sobre el porcentaje de modelos reaprovechables.
4. **Software de orquestación maduro:** Existen prototipos (k3s/postmarketOS, phoneborg, phonon, TESAR-Live, appium-device-farm, scrcpy-farm), pero no una plataforma de "device cloud" de código abierto dominante para cómputo generalista; la mayoría son PoC o herramientas de gestión de granjas de prueba.
5. **Comparativa económica (TCO) completa:** A1 y A2 mencionan análisis de TCO parcial; B1 menciona "fracción del costo" sin desglose público completo. Falta un TCO completo y reciente.
6. **Papers primarios en español/indexados en LatAm:** No se encontraron artículos de conferencia o revista en español (2023–2026) que traten específicamente "reutilización de granja de celulares para cluster ARM". La producción relevante en español se limita a tesis y artículos de acceso abierto no indexados en conferencias top.
7. **Comparativas recientes smartphone-cluster vs. Raspberry Pi / SBC:** Solo aparecen parcialmente (A2 vs Intel/NVIDIA; A5 vs SBCs). Falta un estudio comparativo directo y reciente bajo la misma carga.
8. **Hilos de Reddit completos:** C4, C5, C6 solo se pudieron ver a través de resultados de búsqueda (título, votos, primeras líneas). Reddit bloqueó la lectura completa; detalles de comentarios no verificados.
9. **Fecha del repositorio TESAR-Live (C8):** Página de GitHub no muestra fecha de creación/último commit de forma clara; no puede afirmarse dentro de 2023–2026 con certeza.
10. **Fecha del artículo Hackster (no listado en tabla final):** Fecha exacta no expuesta en la página capturada; se infiere ≈2025.

---

## 5. Recomendación de qué hacer con la información

1. **Para el trabajo del curso, citar como fuentes centrales:**
   - **A1 Junkyard Computing (ASPLOS 2023):** para el argumento de sostenibilidad/reaprovechamiento de e-waste y la tesis de que reutilizar dispositivos existentes amortiza mejor el carbono incorporado que comprar servidores nuevos eficientes. Métrica: hasta 18,9× más eficiente en carbono vs c5.9xlarge tras 3 años.
   - **A2 SoC Cluster / More is Different (USENIX ATC 2024):** para métricas de eficiencia energética (hasta 6,5× más throughput/J en inferencia DL; frames/J; Geekbench vs Graviton). URL verificable en usenix.org y arXiv.
   - **A4 IEEE Pervasive Computing 2025:** como ejemplo real y reproducible de clúster de teléfonos reciclados en funcionamiento (4 teléfonos Nexus, < $10, postmarketOS, despliegue submarino).
   - **A3 ICSCA 2025:** para inferencia distribuida de LLMs en móviles (mejora de 74 % en tiempo de inferencia por token con 4 nodos).
   - **A5 Sensors/MDPI 2025:** para el ángulo de inferencia de IA en clústeres de smartphones reales comparados con SBCs.

2. **Para el contexto práctico y experiencia de implementación:**
   - **C1 blog denv.it (2024):** clúster k3s/postmarketOS con OnePlus, problemas concretos y soluciones (kernel, nftables, device tree).
   - **C9 phoneborg y C10 phonon (2026):** los repos más recientes para clústeres de inferencia LLM sobre teléfonos.
   - **B1 blog Google Research (junio 2026):** anuncio del datacenter de 2.000 Pixels, para contextualizar el interés institucional reciente.

3. **Si el objetivo es una afirmación específica de FLOPS/Watt:** deberá realizarse mediante benchmarking propio (p. ej., Linpack/NPB en un nodo móvil vs nodo de servidor), porque la literatura 2023–2026 no reporta esa métrica de forma estándar para clústeres de smartphones.

4. **Gaps a documentar en el trabajo:** señalar la falta de métricas FLOPS/Watt estandarizadas, la falta de datos de fiabilidad a largo plazo, y la ausencia de literatura primaria en español sobre el tema específico.

---

**Fuentes consultadas:** dl.acm.org, usenix.org, arxiv.org, pmc.ncbi.nlm.nih.gov, computer.org, injoit.org, escholarship.org, research.google, news.ycombinator.com, reddit.com, github.com, blog.denv.it, hackster.io. Fecha de consulta: 17 de noviembre de 2026. Todo lo reportado proviene de fuentes con URL y fecha verificables; nada fue inventado.

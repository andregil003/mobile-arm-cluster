# Papers primarios — métricas FLOPS/Watt y offloading móvil (Informe del agente de investigación)

## 1. Evaluation of mobile ARM-based SoCs for high performance computing
- **Autores:** paper de conferencia (SpringSim 2016)
- **Año:** 2016
- **Conferencia:** SpringSim 2016 — HPC track, ACM / Society for Modeling & Simulation International
- **URL:** https://dl.acm.org/doi/pdf/10.22360/SpringSim.2016.HPC.022 (DOI: 10.22360/SpringSim.2016.HPC.022)
- **Enfoque:** Argumenta que FLOPS/Watt es métrica más adecuada que FLOPS puro para SoCs ARM móviles en HPC, porque la eficiencia energética es el factor limitante.
- **Métricas clave:** FLOPS/Watt como métrica central de evaluación.

## 2. Scalable Smartphone Cluster for Deep Learning
- **Autores:** Byunggook Na, Jaehee Jang, Seongsik Park, Seijoon Kim, Joonoo Kim, Moon Sik Jeong, Kwang Choon Kim, Seon Heo, Yoonsang Kim, Sungroh Yoon
- **Año:** 2021 (submitido 23 Oct 2021)
- **Conferencia:** arXiv preprint (cs.LG / cs.DC)
- **URL:** https://arxiv.org/abs/2110.12172 (DOI: 10.48550/arXiv.2110.12172)
- **Enfoque:** Cluster de smartphones escalable para entrenamiento de DNN, conectando 138 dispositivos Galaxy S10+ mediante red cableada Ethernet. Entrenamiento síncrono de gran lote con Caffe.
- **Métricas clave:** 138 dispositivos Galaxy S10+ interconectados por Ethernet cableado; 90% de la velocidad de una GPU NVIDIA P100 en ResNet-50; ~43x speed-up sobre una GPU NVIDIA V100 en MobileNet-v1; límite inalámbrico ~30 smartphones.

## 3. Towards Green Computing: A Survey of Performance and Energy Efficiency of Different Platforms using OpenCL
- **Autores:** Philip Heinisch, Katharina Ostaszewski, Hendrik Ranocha
- **Año:** 2020
- **Conferencia:** arXiv preprint (cs.PF); publicado en ACM (dl.acm.org/doi/10.1145/3388333.3403035)
- **URL:** https://arxiv.org/html/2003.03794v1
- **Enfoque:** Compara time-to-solution y energy-to-solution en 22 GPUs discretas, 3 GPUs integradas, 14 CPUs de servidor/workstation y 4 CPUs ARM + 2 GPUs ARM integradas, usando OpenCL. Concluye que dispositivos ARM son comparables o mejores en eficiencia energética (energy-to-solution), especialmente en cargas simples como producto punto o procesamiento de señal.
- **Métricas clave:** Energy-to-solution; time-to-solution; potencia vía profilers internos y multímetro digital RMS externo. Dispositivos ARM: energía comparable o inferior a CPUs x86 modernos. GPU Mali G52 comparable en eficiencia a GPUs modernas en punto flotante simple precisión.

## 4. Making the case for computational offloading in mobile device clouds
- **Autores:** Afnan Fahim, Abderrahmen Mtibaa, Khaled A. Harras
- **Año:** 2013
- **Conferencia:** 19th Annual International Conference on Mobile Computing & Networking (MobiCom 2013), ACM
- **URL:** https://dl.acm.org/doi/10.1145/2500423.2504576 ; informe técnico CMU-CS-13-119: http://ra.adm.cs.cmu.edu/cs2013.html
- **Enfoque:** Estudia offloading computacional entre dispositivos móviles que forman un Mobile Device Cloud (MDC). Identifica cinco tecnologías de comunicación (Bluetooth 3.0, Bluetooth 4.0, WiFi Direct, WiFi, 3G) y evalúa experimentalmente el potencial de ganancia del offloading entre dispositivos móviles.
- **Métricas clave:** Cinco tecnologías de offloading comparadas; enfoque experimental con emulación y mediciones reales.

## 5. Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon
- **Autores:** Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto
- **Año:** 2021 (arXiv v1, oct 2021); publicado en ASPLOS 2023
- **Conferencia:** ASPLOS 2023, ACM; preprint arXiv:2110.06870
- **URL:** https://arxiv.org/html/2110.06870v2 ; https://doi.org/10.48550/arxiv.2110.06870 ; PDF: http://kastner.ucsd.edu/wp-content/uploads/2025/06/admin/junkyard.pdf
- **Enfoque:** Reutilización de smartphones desechados como "junkyard computers" para extender su vida útil y reducir carbono incorporado (70-85% de la huella de un smartphone proviene de manufactura). Propone la métrica Computational Carbon Intensity (CCI). Cloudlet real de Pixel 3A comprados en eBay a $65 USD, benchmarkeado con DeathStarBench.
- **Métricas clave:** CCI = (C_M + C_C + C_N) / ops_total. Manufactura = 70-85% de la huella de carbono de ciclo de vida. Consumo de potencia por nivel de CPU (medidor USB): Pixel 3A: P100=2.5W, P50=1.9W, P10=1.4W, P_idle=0.8W, P_avg=1.54W; Nexus 4: P100=3.6W, P50=2.7W, P10=1.0W, P_idle=0.7W, P_avg=1.78W; Thinkpad X1 Carbon: P_avg=11.47W; ProLiant DL380 G6: P_avg=199.1W; PowerEdge R740: P_avg=308.7W. Geekbench multinúcleo: Pixel 3A SGEMM=39.0 Gflops (N=54 para igualar un PowerEdge R740); Nexus 4 SGEMM=8.12 Gflops (N=256).

## 6. Exploring Smartphone-Based Edge AI Inferences Using Real Testbeds
- **Autores:** M. Hirsch y colaboradores
- **Año:** 2025
- **Conferencia:** PMC / Europe PMC (artículo de acceso abierto, citado 9 veces)
- **URL:** https://pmc.ncbi.nlm.nih.gov/articles/PMC12074420/
- **Enfoque:** Compara latencia y eficiencia energética de inferencias de IA en el borde usando testbeds reales de clusters de smartphones versus SBCs exclusivamente. Evalúa configuraciones impulsadas por batería y métricas de inferencia acumulada.
- **Métricas clave:** Latencia de inferencia acumulada; makespan (tiempo total de completación); consumo energético en configuraciones impulsadas por batería.

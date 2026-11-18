# Papers primarios — IEEE/Scholar (Informe del agente de investigación)

## 1. Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon
- **Autores:** Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto (UC San Diego)
- **Año:** 2023 (conferencia); preprint arXiv octubre 2021
- **Conferencia:** ASPLOS '23 — 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems, Vol. 2, pp. 400–412, Vancouver, BC
- **URL/DOI:** arXiv: https://arxiv.org/abs/2110.06870 (DOI: 10.48550/arXiv.2110.06870)
- **Enfoque:** Reutiliza smartphones desechados como "junkyard computers" para evitar fabricar nuevos. Introduce la métrica Computational Carbon Intensity (CCI). Cloudlet real de teléfonos Pixel 3A (eBay, $65 USD) evaluado con DeathStarBench.
- **Métricas clave:** Pixel 3A: 2.5 W (100% CPU), 0.8 W (idle), 1.54 W promedio; Nexus 4: 3.6 W / 0.7 W / 1.78 W; PowerEdge R740: 510 W / 201 W. SGEMM: PowerEdge R740 = 2,070 Gflops vs Pixel 3A = 39.0 Gflops → **54 phones Pixel 3A** para igualar un servidor; Nexus 4 → **256 phones**. Fabricación = 70–85% de la huella de carbono de por vida. CCI = (C_M + C_C + C_N) / ops a lo largo de la vida.

## 2. DroidCluster: Towards Smartphone Cluster Computing
- **Autores:** Felix Büsching, Sebastian Schildt, Lars C. Wolf (TU Braunschweig, Alemania)
- **Año:** 2012
- **Conferencia:** 2012 32nd International Conference on Distributed Computing Systems Workshops (ICDCSW), pp. 114–117 (IEEE)
- **URL/DOI:** IEEE DOI: 10.1109/ICDCSW.2012.59 ; PDF: https://www.ibr.cs.tu-bs.de/papers/buesching-icdcs2012.pdf
- **Enfoque:** Clúster de seis teléfonos Android ejecutando MPI sobre WiFi. Benchmark LINPACK. Concluye que montar un clúster de smartphones es posible y razonable.
- **Métricas clave:** Seis teléfonos Android (LG P500, ARM11 600 MHz). Interconexión solo WiFi (punto de acceso permite teóricamente hasta 1024 nodos). LINPACK sobre WiFi.

## 3. Energy- and Cost-Efficiency Analysis of ARM-Based Clusters
- **Autores:** Zhonghong Ou, B. Pang, Y. Deng, J. K. Nurminen, A. Ylä-Jääski, P. Hui (Aalto / HKUST)
- **Año:** 2012
- **Conferencia:** 12th IEEE/ACM International Symposium on Cluster, Cloud and Grid Computing (CCGrid 2012), Ottawa
- **URL/DOI:** IEEE Xplore: https://ieeexplore.ieee.org/document/6217412 (DOI: 10.1109/CCGRID.2012.84) ; PDF: https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1074.9789&rep=rep1&type=pdf
- **Enfoque:** Analiza clúster ARM vs estación de trabajo Intel x86 en eficiencia energética y costo. Concluye que clústeres ARM son significativamente más eficientes energéticamente, adecuados como servidores de bajo consumo para cargas web reales.
- **Métricas clave:** Ratio de eficiencia energética ARM vs Intel: **2.6x–9.5x**. Eficiencia pico: **1,046 MFLOPS/W**. Consumo total al máximo: ~14 W. Más de 450 peticiones simultáneas y ~1,000 transacciones por segundo. Clúster C: 7.101 Gflops con 8 nodos a 25 W → ~284 MFLOPS/W.

## 4. Reuse of Retired Mobile Devices in Cyber-Physical Systems
- **Autor:** Timothy Ambrose (asesor: Rajeevan Amirtharajah)
- **Año:** tesis/repositorio UC (sin año explícito en índice)
- **Fuente:** eScholarship (repositorio Universidad de California) — https://escholarship.org/uc/item/8cp0h66g
- **Enfoque:** Diseño y caracterización de un sistema que da segundo uso a dispositivos móviles retirados como nodos dentro de un sistema ciberfísico / computadora distribuida.
- **Métricas clave:** No se reportan métricas numéricas específicas en el índice; se centra en diseño y caracterización del sistema.

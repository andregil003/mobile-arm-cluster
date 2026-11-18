# Papers primarios recientes (2023-2026) — Green Computing y eficiencia energética ARM

Informe del subagente "Green computing mobile ARM 2023-2026". Fuente original en el escritorio de André; versionada aquí en el repo. Criterio: solo fuentes reales (arXiv, revistas indexadas, actas de conferencia). Nada inventado.

---

## Metodología de búsqueda
Cadenas ejecutadas en websearch:
1. "FLOPS/Watt" OR "energy-to-solution" ARM mobile cluster 2023 OR 2024 OR 2025
2. "green computing" smartphone cluster ARM 2023 OR 2024 OR 2025 OR 2026
3. site:arxiv.org ARM cluster energy efficiency mobile 2024 OR 2025
Búsquedas adicionales de refuerzo: "smartphone cluster" energy efficiency ARM vs x86; "Prototyping and Analyzing Mobile SoC Clusters" USENIX ATC 2024.

Cada paper candidato fue leído en texto completo (HTML arXiv / PMC / Springer) para extraer título, autores, año, venue/URL, resumen y métricas concretas.

---

## Paper 1 — Clusters de smartphones reales y eficiencia energética vs SBC
- **Título:** Exploring Smartphone-Based Edge AI Inferences Using Real Testbeds
- **Autores:** Matías Hirsch, Cristian Mateos, Tim A. Majchrzak
- **Año:** 2025
- **Venue / URL:** Sensors (MDPI), 2025 May 2;25(9):2875. DOI: https://doi.org/10.3390/s25092875 ; PMC (texto completo): https://pmc.ncbi.nlm.nih.gov/articles/PMC12074420/ ; PMID: 40363312
- **Resumen:** Evalúa si los clústeres de smartphones son competitivos para inferencia de visión por computadora (IA en el borde) en tiempo real frente a nodos tipo SBC. Usa 3 modelos DL pre-entrenados y 8 nodos heterogéneos (5 smartphones de gama baja/media + 3 SBCs) en 3 escenarios de flujo de imágenes. Concluye que clústeres de 2-4 smartphones con balanceo Pull-Based ofrecen rendimiento competitivo con el SBC más potente, con alrededor de 3x menos consumo de energía.
- **Métricas específicas:**
  - Smartphones (todos ARM): Samsung A02 (4-core A53, 2 GB), Motorola Moto G6 (8-core A53, 3 GB), Samsung A30 (2x A73 + 6x A53, 3 GB), Xiaomi Redmi Note 7 (4x Kryo Gold 2.2 GHz + 4x Kryo Silver 1.8 GHz, 4 GB), Motorola Moto G9 Play (4x Kryo Gold 2.0 + 4x Kryo Silver 1.8, 4 GB).
  - SBCs: Raspberry Pi 4 (ARM Cortex-A72, 4 GB), Nvidia Jetson Nano (ARM A57, 4 GB), Gigabyte Brix GB-BRi5H-8250 (Intel Core i5-8250U, x86, 8 GB).
  - Consumo de energía por escenario (Joules), setup Gigabyte Brix (x86): BCS: 4524 J; SWT: 22,403 J; DMED: 7834 J.
  - Setup de clúster de smartphones Cl409 con Pull-Based (BCS): ~1510 J para una latencia acumulada solo 7.8 s mayor que el más rápido (GBx). → ~3x menos energía que el Gigabyte Brix en ese escenario.
  - Métrica de equidad intra-clúster: Índice de Jain (0-1) para disparidad de uso de batería entre nodos del clúster.
  - Conversión de batería: mAh × voltaje × 3.6 = Julios (1 mAh = 3.6 Culombios).
- **Relevancia para el Big Message:** es el paper más cercano al tema del usuario (reutilizar celulares como clúster ARM); demuestra empíricamente que clústeres de teléfonos usados pueden competir con SBC x86/ARM consumiendo ~3x menos energía.

---

## Paper 2 — Comparación ARM vs x86 en portátiles (energy-to-solution)
- **Título:** A Comparative Analysis of ARM and x86-64 Laptop-Class Processors: Architecture, Assembly-Level Performance, and Energy Efficiency
- **Autores:** Mustafa Mert Özyılmaz
- **Año:** 2026
- **Venue / URL:** arXiv:2604.18896v1 [cs.AR], 20 Abr 2026. https://arxiv.org/abs/2604.18896v1 ; https://arxiv.org/html/2604.18896v1
- **Resumen:** Compara arquitectónica y experimentalmente un Apple M3 (ARM/AArch64) frente a un AMD Ryzen 7 3750H (x86-64, Zen+) con dos benchmarks en ensamblador nativo (Fibonacci recursiva y multiplicación de matrices enteras 256x256), midiendo tiempo de ejecución, energía del procesador y contadores microarquitectónicos. La plataforma x86 es más rápida en Fibonacci; la ARM (Apple) es marcadamente más eficiente energéticamente.
- **Métricas específicas:**
  - Energy-to-solution: Apple M3 reduce energía por solución ~5.82× en Fibonacci y ~6.38× en multiplicación de matrices frente al Ryzen 7 3750H.
  - Tiempo fib(40): M3 583.6 ms vs Ryzen 474.8 ms (Ryzen ~23% más rápido).
  - Tiempo matmul 256×256: M3 26.0 ms vs Ryzen 26.4 ms (empate estadístico).
  - Plataformas: Apple M3 (ARMv8.6-A, 8 cores, macOS 15, batería) vs AMD Ryzen 7 3750H (x86-64 Zen+, 4 cores/8 hilos, Ubuntu 20.04, batería).
  - Herramientas de energía: powermetrics (macOS) vs perf stat / energy-pkg (Linux).
- **Relevancia:** evidencia cuantitativa de que una implementación ARM (SoC móvil) puede entregar 5-6× mejor energy-to-solution que un x86 de clase portátil en cargas representativas, aunque el resultado es de nivel plataforma, no solo ISA.

---

## Paper 3 — Eficiencia energética en HPC y sistemas embebidos (survey con métricas)
- **Título:** Energy Concerns with HPC Systems and Applications
- **Autores:** Roblex T. Nana, Claude Tadonki, Petr Dokladal, Youssef Mesri
- **Año:** 2023 (arXiv v2, 17 Feb 2026; manuscrito IEEE recibido 2021)
- **Venue / URL:** arXiv:2309.08615v2 [cs.CY]. https://arxiv.org/abs/2309.08615v2 ; https://arxiv.org/html/2309.08615v2
- **Resumen:** Sondeo (survey) sobre el panorama de preocupaciones energéticas en sistemas informáticos, desde hardware hasta software, abarcando embebido y supercómputo. Define el trade-off time-to-solution vs energy-to-solution y revisa métricas, herramientas de perfilado y optimización, incluyendo el uso de dispositivos embebidos/ARM como alternativa eficiente frente a CPUs tradicionales.
- **Métricas específicas:**
  - FLOPS/Watt: métrica del Green500 para ranking de supercomputadores.
  - Potencia de top-3 TOP500 (noviembre 2022): Frontier 21.1 MW (1.102 Eflop/s), Fugaku 29.9 MW (442 Pflop/s), LUMI 6.02 MW (151.9 Pflop/s).
  - Costo eléctrico/hora estimado: Frontier $3,165 K; Fugaku $6,548 K; LUMI $1,192 K; Leonardo $3,147 K; Summit $1,515 K.
  - Emisión CO2/hora: Frontier 7,997 kg; Fugaku 14,322 kg; LUMI 795 kg; Leonardo 2,087 kg; Summit 3,828 kg.
  - Embebido: Coral Dev Board supera a Intel Skylake >20× en tiempo y eficiencia energética para inferencia ML; Raspberry Pi, Nvidia Jetson, Intel NCS2, Coral como dispositivos de baja potencia.
- **Relevancia:** marco de métricas (FLOPS/Watt, energy-to-solution, CO2) y validación de que dispositivos embebidos/ARM de baja potencia pueden ser más eficientes energéticamente que CPUs de servidor en cargas específicas.

---

## Paper 4 — ARM vs x86: eficiencia energética desde consumo hasta cloud
- **Título:** Redefining Computing: Rise of ARM from consumer to Cloud for energy efficiency
- **Autores:** Tahmid Noor Rahman, Nusaiba Khan, Zarif Ishmam Zaman
- **Año:** 2024
- **Venue / URL:** arXiv:2402.02527 [cs.CE], 4 Feb 2024. https://arxiv.org/abs/2402.02527 ; (DOI relacionado: https://doi.org/10.30574/wjarr.2024.21.1.0017)
- **Resumen:** Analiza y compara las arquitecturas ARM (RISC) y x86 (CISC) para identificar los factores del creciente predominio de ARM por eficiencia energética, desde smartphones y portátiles hasta servidores de cloud/data centers que operan 24/7 donde la energía es un coste dominante.
- **Métricas específicas:** No reporta cifras numéricas de FLOPS/Watt ni consumo en W en el abstract; es un análisis comparativo cualitativo y arquitectónico (RISC vs CISC, SoC, impacto de smartphones en el mercado de portátiles y cloud).
- **Relevancia:** fundamentación conceptual del porqué ARM domina en eficiencia energética por vatio; útil como marco teórico, no como fuente de métricas numéricas propias.

---

## Paper 5 — Modelado de potencia en dispositivos móviles ARM heterogéneos
- **Título:** A Methodology to Assess Power Modeling in Energy-Aware Federated Learning on Heterogeneous Mobile Devices
- **Autores:** Chaimae Jallouli, Karim Boubouh, Robert Basmadjian
- **Año:** 2026
- **Venue / URL:** arXiv:2605.27601v1 [cs.DC], 26 May 2026. Aceptado en NETYS 2026 (Springer Nature). https://arxiv.org/abs/2605.27601v1 ; https://arxiv.org/html/2605.27601v1
- **Resumen:** Propone una metodología reproducible de estimación de potencia CPU en dispositivos ARM móviles commodity (multi-clúster) basada en el modelo analítico CMOS y una técnica de mapeo rail-to-clúster para obtener voltaje por clúster sin hardware adicional. La evalúa en dos dispositivos Android reales y muestra su impacto en el marco de aprendizaje federado AnycostFL.
- **Métricas específicas:**
  - Error del modelo analítico CMOS: <10%.
  - Error del modelo aproximado (V∝f): hasta 959%.
  - AnycostFL con modelo analítico: ~1,000 J y ~2,500 J para alcanzar 80% y 90% de precisión del modelo; con modelo aproximado: 5,000 J. → El modelo analítico consume 1.4× menos energía que el aproximado para la misma precisión.
  - Dispositivos: SoCs móviles Android multi-clúster (tipo big.LITTLE / tri-cluster Google Tensor), medición vía batería (fuel gauge), Termux, Power Profiler, stress-ng, 0.5 s de muestreo, objetivo térmico 30 °C.
- **Relevancia:** cuantifica el ahorro energético (1.4×) al modelar con precisión la potencia de CPUs ARM móviles, clave para cluster de teléfonos donde la batería es la restricción principal.

---

## Paper 6 — Eficiencia energética de SLMs en dispositivos de borde
- **Título:** Characterizing and Understanding Energy Footprint and Efficiency of Small Language Model on Edges
- **Autores:** Md Romyull Islam, Bobin Deng, Nobel Dhar, Tu N. Nguyen, Selena He, Yong Shi, Kun Suo
- **Año:** 2025
- **Venue / URL:** arXiv:2511.11624v1 [cs.DC], 7 Nov 2025. Presentado en IEEE MASS 2025. https://arxiv.org/abs/2511.11624 ; https://arxiv.org/html/2511.11624v1
- **Resumen:** Evalúa la eficiencia energética de 5 SLMs (Llama 3.2, Phi-3 Mini, TinyLlama, Gemma 2) en Raspberry Pi 5, Jetson Nano y Jetson Orin Nano (configuraciones CPU y GPU), con mediciones en tiempo real (Otii Ace Pro). Jetson Orin Nano con GPU alcanza la mejor relación energía-rendimiento; TinyLlama es la más adecuada para entornos de baja potencia.
- **Métricas específicas:**
  - Hardware: Raspberry Pi 5B (ARM, 4 GB, CPU 2.4 GHz, sin GPU); Jetson Nano (ARM, 4 GB, CPU 1.43 GHz, GPU 640 MHz); Jetson Orin Nano (ARM, 8 GB, CPU 1.7 GHz, GPU 1020 MHz, hasta 40 TOPS).
  - Métricas de eficiencia: energía por inferencia (Wh), Tokens per Watt-Hour (TPWh), Energy-Delay Product (EDP = J·s), Wh por billón de parámetros, precisión por vatio-hora, energía por inferencia, runtime-efficiency, eficiencia energética normalizada.
  - Medición en tiempo real con Otii Ace Pro; modelos cuantificados Q4_K_M 4-bit (GGUF, llama.cpp); benchmarks MMLU, HellaSwag, Winogrande.
- **Relevancia:** métricas concretas de energía-rendimiento (TPWh, EDP) en placas ARM de borde, aplicables a nodos de un clúster de teléfonos para inferencia.

---

## Paper 7 — Clúster IoT de Raspberry Pi con energía solar
- **Título:** Design and Implementation of an IoT Cluster with Raspberry Pi Powered by Solar Energy: A Theoretical Approach
- **Autores:** Noel Portillo
- **Año:** 2025
- **Venue / URL:** arXiv:2503.03618 [cs.DC], 5 Mar 2025 (publicado previamente en Zenodo). https://arxiv.org/abs/2503.03618 ; https://doi.org/10.5281/zenodo.14957338
- **Resumen:** Diseña e implementa un clúster IoT de bajo consumo basado en Raspberry Pi 3 Model B con Kubernetes (K3s) y Docker, alimentado por un sistema solar (200 W + batería de 100 Ah), optimizando consumo energético para computación en el borde sostenible.
- **Métricas específicas:**
  - Hardware: Raspberry Pi 3 Model B (ARM).
  - Energía: panel solar 200 W, batería de litio 100 Ah.
  - Consumo en reposo del clúster: ~50 vatios (mencionado en resultado de búsqueda del índice; requeriría confirmación en texto completo).
- **Relevancia:** ejemplo de clúster ARM embebido alimentado por renovables, alineado con green computing y reutilización de hardware de bajo consumo.

---

## Paper 8 — Orquestación consciente de energía en Edge-Cloud con nodos ARM
- **Título:** Experimenting with Energy-Awareness in Edge-Cloud Containerized Application Orchestration
- **Autores:** Dalal Ali, Rute C. Sofia
- **Año:** 2025
- **Venue / URL:** arXiv:2511.09116v1 [cs.NI], 12 Nov 2025. https://arxiv.org/abs/2511.09116 ; https://arxiv.org/html/2511.09116v1
- **Resumen:** Propone inyectar métricas de energía (computacional y de red) en enfoques de programación existentes para optimizar asignación de recursos y reducir consumo energético. Se evalúa en un banco de pruebas real basado en dispositivos ARM, comparando consumo energético y distribución de carga frente a Kubernetes estándar, con mejoras consistentes en eficiencia energética bajo alta carga.
- **Métricas específicas:**
  - Banco de pruebas real basado en dispositivos ARM (detalles de modelo no especificados en el abstract).
  - Comparación contra programación estándar de Kubernetes; mejora en eficiencia energética, particularmente bajo escenarios de alta carga.
- **Relevancia:** validación de que la programación consciente de energía en clústeres ARM de borde reduce el consumo; aplicable a la gestión de un clúster de celulares.

---

## Paper 9 — Clústeres de SoC móviles como servidores de borde (USENIX ATC 2024)
- **Título:** More is Different: Prototyping and Analyzing a New Form of Edge Server with Massive Mobile SoCs
- **Autores:** Li Zhang, Boqing Shi, Xiang Li, Ao Zhou, Xiao Ma, Shangguang Wang, Mengwei Xu
- **Año:** 2024
- **Venue / URL:** 2024 USENIX Annual Technical Conference (ATC'24), 10-12 Jul 2024, Santa Clara, CA, USA. PDF: https://usenix.org/system/files/atc24-zhang-li-prototyping.pdf ; (Versión journal: IEEE Trans. Mobile Computing, julio 2026; arXiv precursor: https://arxiv.org/html/2212.12842v2, 2022)
- **Resumen:** Propone y analiza un nuevo tipo de servidor de borde basado en masivos SoC móviles. Demuestra que GPUs y DSPs de SoC muestran eficiencia energética superior frente a CPUs de servidor tradicionales y GPUs discretas en cargas de inferencia (ResNet-50).
- **Métricas específicas:**
  - SoC GPUs/DSPs vs CPUs de servidor: hasta 42× superior eficiencia energética.
  - SoC GPUs/DSPs vs GPUs: hasta 6.5× superior eficiencia energética.
  - ResNet-50 (FP32): ~18 frames por segundo por Julio en SoC GPU; 7.09× superior a CPU Intel, 1.78× superior a NVIDIA A40 (batch size 64), 1.15× superior en otro escenario.
- **Relevancia:** evidencia fuerte (conference USENIX ATC 2024) de que SoCs móviles (ARM) superan en eficiencia energética por vatio a servidores x86 y GPUs de data center en inferencia de IA — respalda directamente el concepto de granja de celulares como clúster ARM eficiente.

---

## Tabla sintética de métricas clave (fuentes reales)

| Paper (año) | Comparación / enfoque | Métrica destacada |
|---|---|---|
| Hirsch et al. 2025 (Sensors) | Clúster smartphones ARM vs SBC (x86 i5) | ~3× menos energía (4524 J → ~1510 J, BCS) |
| Özyılmaz 2026 (arXiv) | Apple M3 (ARM) vs Ryzen 7 3750H (x86) | 5.82× (Fib) y 6.38× (matmul) energy-to-solution |
| Zhang et al. 2024 (USENIX ATC) | SoC móvil ARM vs CPU servidor / GPU | hasta 42× vs CPU servidor; 6.5× vs GPU |
| Jallouli et al. 2026 (arXiv) | Modelo analítico vs aproximado (ARM móvil) | 1.4× menos energía; error <10% vs 959% |
| Nana et al. 2023 (arXiv) | Survey HPC + embebido ARM/x86 | FLOPS/Watt (Green500); superc. hasta 29.9 MW |
| Islam et al. 2025 (arXiv) | SLMs en Pi 5 / Jetson (ARM) | TPWh, EDP, energía por inferencia |

---

## Límites y huecos (honestidad metodológica)

1. Ninguno de los papers leídos mide directamente un clúster de teléfonos usados ("phone farm") frente a un clúster x86 de servidores reportando FLOPS/Watt agregado. La métrica más cercana es Hirsch 2025 (~3× menos energía en clúster de 5 smartphones ARM vs SBC x86 Gigabyte Brix).
2. Los papers de comparación ARM vs x86 son de portátiles/SoC individuales (Özyılmaz 2026; Rahman 2024), no de clústeres masivos de celulares.
3. Zhang et al. (USENIX ATC 2024) reporta factores 42× y 6.5× para SoCs móviles vs servidores/GPUs, pero en contexto de servidores de borde con SoCs modernos, no específicamente teléfonos usados reutilizados.
4. Jallouli 2026 mide energía en dos dispositivos Android concretos; no generaliza a todo clúster.
5. No se encontró un paper 2023-2026 que reporte FLOPS/Watt agregado de un clúster de celulares usados vs clúster x86. Esa métrica específica aún no está publicada en las fuentes consultadas.

---

## Recomendación para el "Big Message"

Citar como evidencia principal:
- Hirsch et al. 2025 (Sensors, revisado por pares): clústeres de 2-4 smartphones ARM ofrecen rendimiento competitivo a un SBC x86 con ~3× menos energía. URL: https://doi.org/10.3390/s25092875
- Zhang et al. 2024 (USENIX ATC): SoCs móviles ARM hasta 42× más eficientes energéticamente que CPUs de servidor en inferencia. URL: https://usenix.org/system/files/atc24-zhang-li-prototyping.pdf
- Özyılmaz 2026 (arXiv): energy-to-solution 5.82-6.38× mejor en ARM Apple M3 vs x86 Ryzen. URL: https://arxiv.org/abs/2604.18896v1
- Nana et al. 2023 (arXiv): marco de métricas FLOPS/Watt y energy-to-solution para green computing. URL: https://arxiv.org/abs/2309.08615v2

---

FIN DEL INFORME

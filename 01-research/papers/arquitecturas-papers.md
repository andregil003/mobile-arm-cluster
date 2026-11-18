# Papers primarios — arquitecturas, MDC y virtualización (Informe del agente de investigación)

## Verificación de proyectos mencionados (no citables)
- **PhoneStack**: no localizado como source académico verificable (solo listados comerciales).
- **Cinder**: existe como SO consciente de energía para un *único* smartphone (MobiHeld/NSDI ~2010), no como cluster.
- **GreenDC**: empresa ecuatoriana de infraestructura/ciberseguridad, no un paper de cluster.
**Conclusión:** no se citan como papers de clústeres de smartphones.

## 1. DroidCluster: Towards Smartphone Cluster Computing
- **Autores:** Felix Büsching, Sebastian Schildt, Lars Wolf (TU Braunschweig, IBR)
- **Año:** 2012
- **Conferencia:** IEEE ICDCS 2012 — https://ieeexplore.ieee.org/document/6258144/ ; PDF abierto: https://www.ibr.cs.tu-bs.de/papers/buesching-icdcs2012.pdf
- **Enfoque:** Proof-of-concept de 6 nodos Android sin modificar el SO instalado (mínimamente invasivo). Benchmark LINPACK/HPL (HPC estándar).
- **Métricas clave:** 5.81 MFlops por nodo LP500; clúster WiFi alcanza ~75% del valor óptimo (escalado lineal ideal). USB escala ligeramente mejor que WiFi, pero WiFi es competitivo.

## 2. Towards Resource Sharing in Mobile Device Clouds: Power Balancing Across Mobile Devices
- **Autores:** Abderrahmen Mtibaa, Afnan Fahim, Khaled A. Harras, Mostafa H. Ammar
- **Año:** 2013
- **Conferencia:** SIGCOMM Mobile Cloud Computing (MCC) workshop 2013 — https://conferences.sigcomm.org/sigcomm/2013/papers/mcc/p51.pdf
- **Enfoque:** Define Mobile Device Cloud (MDC) como offloading colaborativo entre móviles. Esquemas de offloading que maximizan el lifetime del ensemble (red vive mientras ningún nodo agote batería). Testbed físico con perfiles de potencia realistas.
- **Métricas clave:** Balanceo de energía entre nodos MDC para prolongar lifetime del ensemble.

## 3. Mobile Cloud for Parallel and Distributed Green Computing
- **Autores:** Leszek Siwik, Dawid Kala, Mateusz Godzik, Wojciech Turek, Aleksander Byrski, Marek Kisiel-Dorohinicki (AGH Krakow)
- **Año:** 2017
- **Conferencia/Revista:** Journal of Telecommunications and Information Technology (JTIT) — https://www.jtit.pl/jtit/article/view/690
- **Enfoque:** Mobile Cloud como sistema paralelo y distribuido de móviles interconectados y virtualizados como recurso unificado. Clúster real de smartphones desfasados; compara escalabilidad y eficiencia física vs. virtualizada.
- **Métricas clave:** Escalabilidad y eficiencia del clúster físico vs. conjunto virtualizado.

## 4. Mobile ad hoc cloud: A survey
- **Autores:** Wiley
- **Año:** 2016
- **Conferencia/Revista:** Wireless Communications and Mobile Computing, Wiley — DOI: 10.1002/wcm.2709 (~100 citaciones)
- **Enfoque:** Sondeo del estado del arte en mobile ad hoc cloud (MAC). Taxonomía por componentes arquitectónicos, aplicaciones, objetivos, scheduling, tecnologías de formación y tipos de nodo.
- **Métricas clave:** Encuesta cualitativa/taxonómica; desafíos abiertos (incentivos, heterogeneidad, movilidad, seguridad, privacidad).

## 5. Renee: New Life for Old Phones
- **Autores:** Jennifer Switzer, Eric Siu, Subhash Ramesh, Ruohan Hu, Emanoel Zadorian, Ryan Kastner (UC San Diego)
- **Año:** 2022
- **Conferencia/Repositorio:** UC San Diego ESL 2022 — https://kastner.ucsd.edu/wp-content/uploads/2022/05/admin/esl22-Renee.pdf
- **Enfoque:** Clúster de smartphones usados con Function-as-a-Service (FaaS). Reemplazan Android por Ubuntu Touch (teléfonos como máquinas Linux estándar). Nodo de gestión central (Raspberry Pi) como único punto de entrada. Robusto a fallos multi-teléfono.
- **Métricas clave:** Job `fib`: 1.5–1.9× más rápido que AWS Lambda. Overhead de gestión de clúster: 0.44–0.76 s adicionales.

## 6. Junkyard Computing: Repurposing Discarded Smartphones to Minimize Carbon
- **Autores:** Jennifer Switzer, Gabriel Marcano, Ryan Kastner, Pat Pannuto (UC San Diego)
- **Año:** 2023
- **Conferencia:** ASPLOS '23 — DOI: 10.1145/3575693.3575710 ; PDF: https://kastner.ucsd.edu/wp-content/uploads/2023/03/admin/asplos23-junkyard.pdf
- **Enfoque:** Cloudlet de prueba de 10 teléfonos Pixel 3A / 3A XL con Ubuntu Touch modificado para Docker (módulos BTRFS). Docker Swarm + DeathStarBench. Métrica Computational Carbon Intensity (CCI).
- **Métricas clave:** ~1.7 W/teléfono; 10 dispositivos ≈ 17 W. Costo 3 años: $1,027.60 (clúster) vs $40,404 (AWS c5.9xlarge). Eficiencia de carbono vs c5.9xlarge: 18.9× (SocialNetwork-Write), 9.8× (SocialNetwork-Read), 12.6× (HotelReservation). Throughput: 4,000 QPS (HotelReservation).

## 7. Data Centers from Discarded Cell Phones
- **Autores:** Jennifer Switzer, Eric Siu, Subhash Ramesh, Ruohan Hu, Emanoel Zadorian (UC San Diego)
- **Año:** 2022
- **Conferencia/Repositorio:** CPDC Final Project Report UC San Diego — https://kastner.ucsd.edu/ryan/wp-content/uploads/sites/5/2022/03/admin/phonedatacenter_37430_4689120_237D_Final_Project_Report_CPDC.pdf
- **Enfoque:** Proof-of-concept de data center de smartphones con gestión de clúster basada en Raspberry Pi y SO móvil no tradicional. Evalúa tiempo de respuesta, fiabilidad y eficiencia energética.
- **Componentes:** gestor central Raspberry Pi + banco de teléfonos usados como trabajadores.

## 8. A low-carbon computing platform from your retired phones (Google Research)
- **Autores:** Google Research
- **Año:** 2026 (publicado 12 junio 2026)
- **Repositorio:** https://research.google/blog/a-low-carbon-computing-platform-from-your-retired-phones/
- **Enfoque:** Extraer placas base de teléfonos retirados, agruparse en clústeres y re desplegarlas como plataforma de cómputo de propósito general.
- **Métricas clave:** Clúster moderado de 20 teléfonos soporta tasas de envío pico para una clase de 75+ estudiantes con latencias de calificación por debajo del backend predeterminado de AWS; 1,000 teléfonos soportarían cien clases simultáneas.

## 9. Virtualización sin root en Android — PRoot
- **Fuente oficial:** https://proot-me.github.io/
- **Fuente:** Termux Wiki — https://wiki.termux.com/wiki/PRoot
- **Fuente:** termux/proot-distro (GitHub) — https://github.com/termux/proot-distro
- **Descripción:** Implementación en espacio de usuario de chroot, mount --bind y binfmt_misc sin privilegios de root. Permite ejecutar rootfs distinto (incluido ARM bajo qemu) dentro del espacio de usuario del dispositivo anfitrión. Mecanismo base para correr distribuciones Linux completas en Android sin rootear.
- **Nota:** No se encontró paper primario que valide PRoot como capa de clúster ARM; viable como capa de contenedores por nodo, combinarse con orquestador externo.

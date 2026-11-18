# mobile-arm-cluster

Reutilización de dispositivos móviles obsoletos como clústeres de cómputo distribuido ARM — Estado del arte y caso de estudio.

## Problema
Los dispositivos móviles (celulares y tablets) se desechan masivamente por obsolescencia programada, aunque sus SoCs ARM modernos cuentan con múltiples núcleos y aceleradores dedicados. Paralelamente, los clústeres x86 tradicionales implican alto costo energético e de infraestructura para tareas ligeras o de borde. No existe un estado del arte reciente que sintetice cómo reutilizar esos dispositivos como clústeres de cómputo distribuido ARM, evaluando topologías de red inalámbrica, virtualización sin root y métricas de eficiencia energética (FLOPS/Watt).

## Motivación práctica (caso de estudio)
Este repositorio documenta una arquitectura real en operación: **OpenCode Fleet** — 4 nodos Android (moto-g56-5g, moto-g54-5g, Redmi Note 9, Lenovo Tab M11) ejecutando Ubuntu proot-distro + `opencode serve`, interconectados mediante SSH y Tailscale a través de un MikroTik hAP ax lite con redes segmentadas, con un servidor central 24/7 (desktop-lkl1r8l, i5) y una estación principal de cómputo (andrepc, Ryzen 7 / 22 GB RAM).

## Objetivos del proyecto (curso PI3 — Ing. Jorge Lara)
- **Objetivo general:** Realizar un *review paper* (estado del arte) bajo formato IEEE sobre la reutilización de dispositivos móviles obsoletos como clústeres de cómputo distribuido ARM, sintetizando arquitecturas, eficiencia energética y orquestación en red, con la arquitectura OpenCode Fleet como caso de estudio y motivación.
- **Semana 2 (23–27 nov):** Localizar, leer y resumir 10 papers primarios (IEEE, ACM, arXiv) sobre Mobile Device Clouds / smartphone clusters / Green ARM Computing, y armar una tabla matriz de revisión.
- **Semana 3 (30 nov–4 dic):** Definir el Big Message, estructura IEEE y redacción del paper integrando el estado del arte con el caso de estudio real.
- **Semana 4 (7–11 dic):** Revisión QA, formato IEEE final y entrega del paper.

## Estructura del repositorio
```
mobile-arm-cluster/
├── README.md
├── DECISIONES.md
├── CHANGELOG.md
├── 01-research/          # Búsqueda y resumen de los 10 papers (Semana 2)
├── 02-paper/             # Paper review en formato IEEE (Semanas 3-4)
├── 03-caso-estudio/      # Documentación de la arquitectura real OpenCode Fleet
└── 04-entregables/       # Presentaciones y entregables del curso
```

## Licencia
Público. Trabajo académico del curso Prácticas de Investigación 3.

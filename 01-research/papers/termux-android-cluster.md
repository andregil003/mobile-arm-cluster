# Proyectos reales de cluster ARM de teléfonos — Termux / Android nodos distribuidos

Informe del subagente "Termux Android cluster distributed computing". Criterio de inclusión: solo fuentes verificables (GitHub, paper, blog técnico, noticia). Nada inventado.

---

## 1. Proyectos que usan teléfonos como nodos de cluster (más cercanos al caso)

### 1.1 android-ai-agent-cluster — Ishuin (GitHub)
- **Autor/proyecto:** Ishuin — https://github.com/Ishuin/android-ai-agent-cluster
- **Año:** no indicado en la fuente (repo GitHub, sin fecha de publicación visible)
- **URL:** https://raw.githubusercontent.com/Ishuin/android-ai-agent-cluster/main/docs/agents.md
- **Dispositivos:** 2 (Redmi Note 8 Pro = "edge agent"; Samsung A52 = "worker agent")
- **Arquitectura / orquestación:** Agentes ligeros autónomos sobre Termux. Edge Agent corre `llama-server` (llama.cpp) con Qwen3.5 4B Instruct Q4_K_M, CPU-only, puerto 8080, contexto 2048, health `GET /health`, inferencia `POST /completion`. Worker Agent corre `app.py` (servidor HTTP de Python stdlib) en puerto 8000 que proxyea al edge (`POST /infer`). Comunicación JSON sobre HTTP. Auto-arranque mediante scripts de boot de Termux (`~/.termux/boot/*.sh`) vía Termux:Widget. Monitoreo remoto por túneles trycloudflare.
- **Métricas clave:** carga del modelo ~30 s; timeout Worker→Edge 120 s; Worker→Cliente 300 s; un reintento ante fallo.

### 1.2 PhoneBorg — dzaczek (GitHub, proof of concept)
- **Autor/proyecto:** dzaczek — https://github.com/dzaczek/phoneborg
- **Año:** no indicado explícitamente; activo en 2026 (insignia Go 1.25, 193 commits)
- **URL:** https://github.com/dzaczek/phoneborg
- **Dispositivos:** 5 en cluster de producción (Pixel 8 Pro 12 GB, OnePlus 10 Pro 12 GB, POCO F3 8 GB, Xiaomi Mi 8 6 GB, Xiaomi MI 9 6 GB) + teléfonos emulados (redroid) para tests.
- **Arquitectura / orquestación:** Zero-touch provisioning sobre ADB (no se instala nada manual en el teléfono): un provisioner (`pcprov`) detecta el USB, empuja el node-agent, llama.cpp y un modelo GGUF. Cada teléfono sirve un endpoint OpenAI-compatible. Un controller en Go (un solo proceso) hace gateway, registro, catálogo, placement, failover y affinidad de sesión; expone API web, `pbctl` (CLI), y métricas a Prometheus/Grafana. Modos: un teléfono por petición, pools (`spread`), Super Borg (un teléfono orquesta a varios en paralelo), Big Brain (llama.cpp RPC, un modelo grande partido en capas entre teléfonos), y jobs/MCP (agentes tipo opencode usan el cluster como herramientas). Soporta nodos externos (LM Studio, Ollama, llama-server).
- **Métricas clave:** generación OnePlus 10 Pro: 29,0 / 13,3 / 4,6 / 2,9 tok/s para 0,5B/1,5B/4B/8B (Q4_K_M); failover bajo carga: 0 fallos de 1138 peticiones; 3 tareas en paralelo: 9,9 s en pool vs 23,8 s en un teléfono; Big Brain gpt-oss-20b: ~2,6–2,8 tok/s en 2 teléfonos (carga 9 min). Nota: no usa Termux (instala agente vía ADB), pero es el proyecto de cluster ARM de teléfonos más documentado con integración opencode/MCP.

### 1.3 Phonon — chezgoulet (GitHub, Apache-2.0)
- **Autor/proyecto:** chezgoulet — https://github.com/chezgoulet/phonon
- **Año:** 2026 (versión v0.1.15; reconstrucción de un proyecto previo de 2026)
- **URL:** https://github.com/chezgoulet/phonon
- **Dispositivos:** 1 medido (Google Pixel 7 `panther`); docs de multi-nodo existen pero "aún no se ha medido un segundo teléfono".
- **Arquitectura / orquestación:** App Android que empaqueta `llama-server` (llama.cpp compilado de submódulo), descarga GGUF al almacenamiento de la app, supervisa el servidor como servicio en primer plano y expone API OpenAI-compatible en LAN (puerto 8080). Gateway: LiteLLM (routing, reintentos, timeouts, métricas). Worker: `opencode` en el host apunta al gateway, nunca al teléfono directamente. Forma: `opencode (host) → LiteLLM gateway → phone-a:8080 → phone-b:8080`. Kiosk/Device Owner, pausa térmica, benchmark on-device, export de reporte de dispositivo.
- **Métricas clave:** Pixel 7, Qwen3.5-2B Q4_K_M, contexto 32K: 14,01 tok/s (burst), 10,54 tok/s sostenido en 38 generaciones / 15 min; una vuelta agente (prompt 2,3K + 128 tokens) en 29,0 s.

---

## 2. Proyectos de cluster de teléfonos que NO usan Termux (arquitectura diferente, útiles como referencia)

### 2.1 "Self-Hosting A Cluster On Old Phones" — Hackaday (Denys)
- **Autor/proyecto:** Bryan Cockfield (Hackaday), proyecto de Denys — https://hackaday.com/2025/04/09/self-hosting-a-cluster-on-old-phones/
- **Año:** 9 de abril de 2025
- **URL:** https://hackaday.com/2025/04/09/self-hosting-a-cluster-on-old-phones/
- **Dispositivos:** 3 teléfonos
- **Arquitectura / orquestación:** Requiere bootloader desbloqueable e instalación de postmarketOS (Linux completo para smartphones). Acceso por SSH y Kubernetes para el cluster de cómputo; servicios autocospedados. No es Termux ni Android userland: es Linux nativo sobre hardware del teléfono.
- **Métricas clave:** no reporta cifras de rendimiento; argumenta ahorro vs Raspberry Pi y reutilización de teléfonos con pantallas rotas.

### 2.2 "phone cluster computing" — UC San Diego respaldado por Google (Data Center Dynamics)
- **Autor/proyecto:** Zachary Skidmore / Data Center Dynamics; proyecto de UC San Diego + Google — https://datacenterdynamics.com/en/news/google-backs-uc-san-diego-project-to-build-computing-cluster-from-2000-old-smartphones/
- **Año:** 17 de junio de 2026
- **URL:** https://datacenterdynamics.com/en/news/google-backs-uc-san-diego-project-to-build-computing-cluster-from-2000-old-smartphones/
- **Dispositivos:** 2.000 teléfonos Pixel retirados; organizados en clústeres autogestionados de 25–50 unidades; ~50 servidores-equivalentes en total.
- **Arquitectura / orquestación:** Se despojan los teléfonos hasta la placa base, se reemplaza Android por una distribución Linux de propósito general y se gestionan con Kubernetes (despliegue, escalado y gestión de contenedores). Destinado a clases universitarias (cómputo paralelo, programación de sistemas); lanzamiento previsto otoño 2026. Pruebas tempranas con un clúster de 20 teléfonos manejaron picos de envío de una clase de 75+ estudiantes con latencia de calificación inferior a un backend comparable de AWS.
- **Métricas clave:** la placa base del smartphone ≈ 50 % del carbono incorporado; 25–50 teléfonos ≃ 1 servidor; 2.000 teléfonos ≃ 50 servidores-equivalentes.
- **Nota:** es Linux sobre metal desnudo, no Termux/Android userland; es la referencia de mayor escala.

### 2.3 AAliKKhan/opencode-multi-agent-farm (GitHub) — adyacente, no nodos Android
- **Autor/proyecto:** AAliKKhan — https://github.com/AAliKKhan/opencode-multi-agent-farm
- **Año:** no indicado
- **URL:** https://github.com/AAliKKhan/opencode-multi-agent-farm
- **Dispositivos:** los agentes corren en Windows PC; el Android solo es consola de control remoto (OpenCode Mobile + Tailscale).
- **Nota:** no cumple el requisito de "teléfono como nodo de cómputo"; se menciona solo por cercanía temática con "fleet" de opencode.

---

## 3. Tecnología habilitante (rootless Linux en Android / Termux)

### 3.1 termux/proot-distro (GitHub / PyPI)
- **Autor/proyecto:** termux — https://github.com/termux/proot-distro
- **Año:** publicado 2020-07-20; última release v5.10.3 (PyPI)
- **URL:** https://github.com/termux/proot-distro
- **Dispositivos:** N/A (utilidad por dispositivo)
- **Arquitectura / orquestación:** Capa de gestión de contenedores Linux rootless en Termux (y hosts Linux normales) usando `proot` (ptrace-based chroot/bind-mount) sin root, sin módulos de kernel, sin Docker daemon. Instala distribuciones desde imágenes OCI/Docker Hub (Ubuntu, Debian, Alpine, Arch, openSUSE…) o tarballs locales. Soporta cross-arch con QEMU user-mode (aarch64, arm, i686, x86_64, riscv64). Puede construir imágenes OCI desde Dockerfile sin Docker. Comandos: `proot-distro install/ubuntu`, `login`, `run`, `build`.
- **Limitaciones declaradas:** rendimiento inferior por interceptación ptrace de cada syscall; no hay cgroups ni namespaces reales; no hay systemd/OpenRC como supervisor (solo procesos sueltos); no hay anidación de proot; Android bloquea algunos `/proc` (se usan valores estáticos). Es la base técnica que permite correr Ubuntu/Debian (y por tanto `opencode serve`) en Termux sin root.

---

## 4. Referencia académica sobre reutilización de móviles (seguridad + sostenibilidad)

### 4.1 Roty, Mühlberg, Determe — arXiv:2606.06181
- **Título:** Opportunities and Challenges in Securely Reusing and Repurposing Mobile Devices
- **Autores:** Adelin Roty, Jan Tobias Mühlberg, Jean-François Determe (École Polytechnique de Bruxelles / ULB, Bruselas)
- **Año:** 05 junio 2026 (v2); 12th Workshop on Computing within Limits
- **URL:** https://arxiv.org/html/2606.06181
- **Dispositivos:** caso de estudio PinePhone (PINE64, Allwinner A64, Arm Cortex-A53 con TrustZone)
- **Contenido:** analiza si los mecanismos de seguridad hardware-backed (secure boot, TEE/TrustZone, secretos hardware-bound) siguen siendo efectivos al repurificar un smartphone fuera de su ecosistema vendor. Concluye que se necesita reconstruir anclajes de confianza a bajo nivel y soporte del proveedor. Cita a Switzer et al. (2023), que acuñó el término "junkyard computing" y concluye que para "cargas de trabajo específicas, clústeres de teléfonos repurificados son más baratos y más eficientes en carbono que servidores tradicionales". No describe un clúster construido, pero es la referencia académica que valida el enfoque de granja de celulares como recurso de cómputo.
- **Métricas clave:** 5.300 millones de teléfonos como residuos electrónicos en 2022 (WEEE Forum); vida media del smartphone ~3 años.

---

## 5. Experiencias de comunidad (menor rigor, pero documentadas)

### 5.1 Reddit r/termux — "distributed AI worker integration ... entirely on my Android phone (using Termux)"
- **Título:** I wrote a distributed AI worker integration for an open-source repo entirely on my Android phone (using Termux)
- **Autor:** usuario `1teohel`, r/termux — https://www.reddit.com/r/termux/comments/1teohel/i_wrote_a_distributed_ai_worker_integration_for
- **Año:** no indicado
- **URL:** https://www.reddit.com/r/termux/comments/1teohel/i_wrote_a_distributed_ai_worker_integration_for
- **Contenido:** trabajadores en Termux que hacen *polling* saliente por jobs (no abren puertos entrantes); reclamación atómica de tareas, de modo que de 3 trabajadores Termux solo uno agarra cada tarea.
- **Nota:** fuente de comunidad (Reddit), sin métricas públicas; se incluye como experiencia anecdótica alineada con la arquitectura del usuario.

---

## 6. Síntesis aplicada a tu caso (4 nodos Android + Termux + proot-distro + opencode serve)

| Proyecto | ¿Usa Termux? | ¿Nodos = teléfonos? | Orquestación | Más relevante para ti |
|---|---|---|---|---|
| Ishuin android-ai-agent-cluster | Sí | Sí (2) | JSON/HTTP edge+worker, boot scripts Termux | Patrón de agente distribuido sobre Termux |
| PhoneBorg | No (ADB) | Sí (5) | Controller Go + gateway OpenAI + failover/pools | Mejor referencia de cluster ARM de teléfonos con opencode/MCP |
| Phonon | No (app propia) | Sí (1 medido) | LiteLLM gateway + opencode host | Patrón gateway + opencode sobre teléfonos |
| UCSD/Google | No (Linux+K8s) | Sí (2000) | Kubernetes | Referencia de escala, no aplicable a Termux |
| proot-distro | Sí | N/A | Rootless containers en Termux | Tu base técnica actual (Ubuntu en Termux) |

**Recomendación de lectura para replicar/extendir tu setup:**
1. **PhoneBorg** (docs: `CONCEPTS.md`, `BENCHMARKS.md`, `PBCTL.md`) para ideas de placement, failover, pools y cómo integrar opencode vía MCP sobre teléfonos.
2. **Ishuin android-ai-agent-cluster** (`docs/agents.md`, `docs/deployment.md`) para ver cómo arrancar agentes al boot con Termux:Widget y cómo separar edge (inferencia) de worker (API) en Termux.
3. **termux/proot-distro** para los límites reales de correr Ubuntu bajo proot en tus 4 nodos (sin cgroups, sin systemd, rendimiento por ptrace) al dimensionar cargas de `opencode serve`.

**Fuentes no verificadas / no incluidas intencionalmente:** Switzer et al. 2023 ("junkyard computing") solo se cita dentro de arXiv:2606.06181, no se accedió a la fuente primaria, por lo que se reporta tal cual como cita secundaria. Cualquier dato de métrica no citado arriba ha sido omitido para evitar inventar.

---
*Informe entregado como texto plano estructurado. Todas las URLs son accesibles y los datos se extrajeron directamente de las fuentes listadas.*

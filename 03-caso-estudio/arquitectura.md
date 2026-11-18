# Arquitectura del caso de estudio — OpenCode Fleet

## Nodos móviles (4 agentes vía SSH puerto 8022)
- moto-g56-5g (Tailscale 100.89.95.53)
- moto-g54-5g (Tailscale 100.67.60.97)
- m2003j15sc / Redmi Note 9 (Tailscale 100.84.194.2, u0_a253)
- lenovo-tab-m11-jagl (Tailscale 100.73.63.114)

Cada uno ejecuta:
- Termux + Ubuntu proot-distro
- `opencode serve --port 4096` (API headless de OpenCode)
- SSH en puerto 8022

## Servidor central 24/7
- desktop-lkl1r8l (Tailscale 100.65.166.48) — i5, backend + interfaz web tipo Discord, Bun + Hono

## Estación principal de cómputo y almacenamiento
- andrepc (Tailscale 100.82.59.14 / LAN 192.168.88.250) — Ryzen 7 / 22 GB RAM, nodo trabajador principal y almacén de proyectos

## Red y conectividad
- Interconexión por Tailscale (red privada virtual en malla)
- MikroTik hAP ax lite con redes Wi-Fi segmentadas (Casa directa vs. Secure-WARP con Cloudflare)
- Kill Switch contra fugas hacia el ISP (Tigo)

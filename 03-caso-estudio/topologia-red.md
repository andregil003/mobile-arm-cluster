# Topología de red — MikroTik hAP ax lite + Cloudflare One / Tailscale

## Redes Wi-Fi
- **WiFi-Casa (192.168.88.0/24):** salida directa por Tigo, DNS cifrado DoH
- **WiFi-Secure-WARP (192.168.99.0/24):** tráfico 100% cifrado por túnel WireGuard wg-warp, Kill Switch estricto

## Enrutamiento
- Ruta por defecto hacia Cloudflare WARP (tabla `to-warp`)
- Retorno de rutas para Tailscale (100.64.0.0/10 vía 192.168.88.250)
- Policy-Based Routing para nodos específicos por el túnel WARP

## Seguridad
- Normalización de TTL (oculta múltiples dispositivos tras el NAT)
- Aleatorización de MAC en ether1 hacia el router de Tigo
- Reglas de Firewall Raw contra escaneo de puertos y fuerza bruta

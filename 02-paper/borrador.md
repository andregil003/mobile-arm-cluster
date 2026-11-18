# Borrador del paper IEEE — Reutilización de dispositivos móviles como clústeres ARM

## Esquema propuesto (formato IEEE)

1. **Título** (tentativo): Reutilización de Dispositivos Móviles Obsoletos como Clústeres de Cómputo Distribuido ARM: Revisión del Estado del Arte en Arquitecturas, Eficiencia Energética y Orquestación en Red
2. **Abstract**
3. **Intromisión** — problema de e-waste, costo energético x86, oportunidad ARM móvil
4. **Estado del arte** — síntesis de los 10 papers (Mobile Device Clouds, smartphone clusters, Green Computing)
5. **Big Message** — dispositivos ARM desechados tienen FLOPS/Watt competitivo para cargas de borde paralelizables si se resuelven latencia de red, gestión térmica/batería y aislamiento de espacio de usuario
6. **Arquitecturas y topologías de red** — Wi-Fi vs. Ethernet, SSH, VPNs en malla (Tailscale)
7. **Virtualización sin root** — PRoot, contenedores, espacio de usuario en Android
8. **Caso de estudio: OpenCode Fleet** — arquitectura real de André (4 nodos Android + servidor central 24/7 + MikroTik hAP ax lite)
9. **Métricas y evaluación** — FLOPS/Watt, speedup, latencia, throughput
10. **Conclusiones**
11. **Referencias** (los 10 papers de la Semana 2)

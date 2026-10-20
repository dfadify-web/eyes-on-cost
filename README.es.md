# Eyes on Cost

**Extensión de [Eyes on Claude](https://github.com/dfadify-web/eyes-on-claude).** Lo que costarían tus sesiones de Claude Code en la API, en directo: tokens reales por respuesta, acierto y ahorro de caché, gasto por sesión, modelo y minuto.

[English](README.md)

![Eyes on Cost](docs/screenshot.png)

## Qué hace

- Gasto equivalente en la API a partir del `usage` real de cada respuesta (entrada, escritura y lectura de caché, salida).
- Porcentaje de acierto de la caché y dinero ahorrado.
- Ritmo de gasto ($/h de los últimos 10 min), gráfica acumulada y por minuto.
- Gasto por sesión, por modelo y las peticiones más caras.
- Tabla de precios oficial de Anthropic (Opus 5.5, Sonnet 5.5, Haiku 5.5, Fable 5.1, 4.x…).

Todo sale del stream real de Eyes on Claude (los transcripts de Claude Code): nada se inventa.

## Instalar

Requiere Eyes on Claude **v2.3+** y Node 18+.

```bash
npx -y github:dfadify-web/eyes-on-cost
```

Abre Eyes on Claude → **Extensiones** → **Eyes on Cost** (`http://localhost:7777/#ext/eyes-on-cost`). Desinstalar: `npx -y github:dfadify-web/eyes-on-cost --uninstall`.

Suelta: `node server.js` → `http://localhost:7779` (necesita Eyes on Claude en :7777).

## Cómo funciona

Un servidor Node sin dependencias (`server.js`) sirve `public/` y reenvía el stream en vivo `/events` de Eyes on Claude. Solo escucha en 127.0.0.1.

MIT © dfadify-web

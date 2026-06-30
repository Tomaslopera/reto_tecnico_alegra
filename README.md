# Sistema de Detección Temprana de Bloqueos · Alegra

Reto técnico para el rol de AI Operations Analyst. Pipeline en n8n que detecta señales de riesgo en proyectos antes de que se conviertan en bloqueos formales.

https://cute-eclair-ed3500.netlify.app/

## Flujos

### Flujo 01 — Detección temprana de bloqueos
`Alegra – Deteccion Temprana de Bloqueos.json`

Lee el estado del proyecto desde Google Sheets, calcula métricas de desviación en JavaScript, analiza los comentarios de texto libre con GPT-4o y envía un reporte de semáforo por Gmail. Si detecta señal crítica en la ruta crítica T1→I→II→III→V dispara una alerta inmediata con el impacto en cadena estimado.

![Detección de Bloqueos](Captura de pantalla 2026-06-26 a la(s)
6.30.45p.m..png)

### Flujo 02 — Analizador de transcripciones
`Alegra – Analizador de Transcripciones.json`

Recibe la URL de cualquier Google Doc con la transcripción de una reunión, la lee desde Drive, la analiza con GPT-4o e identifica riesgos, acuerdos y recomendaciones antes de que lleguen al reporte formal.

```
Webhook → Google Drive (por URL) → AI Agent (GPT-4o) → Gmail (resumen ejecutivo)
```
## Demo

`index.html` — interfaz para activar ambos flujos en tiempo real desde el navegador.

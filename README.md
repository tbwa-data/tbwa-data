# 📊 TBWA Data Intelligence - Listening Hub & Voto Informado

Este repositorio centraliza la orquestación de datos entre los motores de extracción (**Onclusive**, **Google Alerts**) y el ecosistema de **Supabase / Lovable**. Automatiza la ingesta, limpieza de sentimientos y categorización de menciones para el mercado peruano.

---

## 🚀 Matriz de Sincronización (Estado Actual)

| Proyecto | Motor de Extracción | Estado Actual | Logs de Ejecución |
| :--- | :--- | :--- | :--- |
| **Listening Hub x iO** | **Google Alerts (Noticias)** | [![Google Alerts History Sync](https://github.com/tbwa-data/alerts-supabase/actions/workflows/google_alerts_sync.yml/badge.svg)](https://github.com/tbwa-data/alerts-supabase/actions/workflows/google_alerts_sync.yml) | [Ver historial](https://github.com/tbwa-data/alerts-supabase/actions) |
| **Listening Hub x iO** | **Onclusive (iO Social)** | [![Actualizar Dashboard iO Social](https://github.com/tbwa-data/onclusive-to-supabase/actions/workflows/main.yml/badge.svg)](https://github.com/tbwa-data/onclusive-to-supabase/actions/workflows/main.yml) | [Ver historial](https://github.com/tbwa-data/onclusive-to-supabase/actions) |
| **Voto Informado** | **Onclusive (Sincronización)** | [![Sincronización Voto Informado](https://github.com/tbwa-data/VotoInformado---Onclusive-to-Supabase/actions/workflows/voto_informado.yml/badge.svg)](https://github.com/tbwa-data/VotoInformado---Onclusive-to-Supabase/actions/workflows/voto_informado.yml) | [Ver historial](https://github.com/tbwa-data/VotoInformado---Onclusive-to-Supabase/actions) |

---

## 🛠️ Arquitectura Técnica

### 1. Extracción (Python & GitHub Actions)
- **Frecuencia:** Ejecución programada cada 4 horas (o manual vía Actions).
- **Lógica:** Scripts de Python que consumen la API de **Onclusive (Digimind)** y normalizan los campos antes de enviarlos a la base de datos.
- **Campos Clave:** `id`, `Detail`, `Publish date`, `"Sentiment"`, `media_type`, `Reach`, `Audience`.

### 2. Procesamiento (Supabase Triggers & Functions)
- **Normalización:** Los datos se estandarizan a `"Sentiment"` (Mayúscula) y `media_type` (snake_case) para consistencia profesional en reportes.
- **Agregación:** Un Trigger en la tabla `voto_informado` procesa automáticamente los datos hacia `voto_informado_agrupado`, permitiendo visualizaciones de alta velocidad en el Dashboard.

### 3. Visualización (Lovable / Frontend)
- Dashboard reactivo que consume directamente las vistas agregadas de Supabase.
- Manejo de seguridad para tipos de datos `undefined` o vacíos.

---

## 📝 Notas de Mantenimiento (Data Team)

> [!IMPORTANT]
> **Case Sensitivity:** Todas las referencias al sentimiento en la base de datos DEBEN usar comillas dobles y mayúscula: `"Sentiment"`. El campo de medios debe usarse como `media_type`.

**Contacto de emergencia:** André Pérez - Data Scientist (TBWA Team)

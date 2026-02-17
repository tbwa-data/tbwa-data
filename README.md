# TBWA Data Intelligence Hub

Bienvenido al centro de monitoreo de datos. Aquí puedes supervisar la salud de los pipelines que alimentan el dashboard de **iO**.

### System Health Monitor (Real-time)

| Motor de Extracción | Estado Actual | Logs de Ejecución |
| :--- | :--- | :--- |
| **Google Alerts (Noticias)** | [![Google Alerts History Sync](https://github.com/tbwa-data/alerts-supabase/actions/workflows/google_alerts_sync.yml/badge.svg)](https://github.com/tbwa-data/alerts-supabase/actions/workflows/google_alerts_sync.yml) | [Ver historial](https://github.com/tbwa-data/alerts-supabase/actions) |
| **Onclusive (iO Social)** | [![Actualizar Dashboard iO Social](https://github.com/tbwa-data/onclusive-to-supabase/actions/workflows/main.yml/badge.svg)](https://github.com/tbwa-data/onclusive-to-supabase/actions/workflows/main.yml) | [Ver historial](https://github.com/tbwa-data/onclusive-to-supabase/actions) |

---

### Arquitectura del Ecosistema
* **Data Sources:** Google Alerts (RSS) & Onclusive API.
* **Pipeline:** GitHub Actions (Python scripts).
* **Database:** Supabase (PostgreSQL).
* **Frontend:** Lovable (React/Vite).

---
*Última actualización manual del sistema: febrero 2026*

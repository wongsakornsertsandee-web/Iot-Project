# Real-Time IIoT Telemetry & Environmental Automation System

An automated cloud-based Industrial IoT (IIoT) monitoring and control system built with **Node-RED** and **JavaScript**. The platform ingests real-time environmental telemetry data via REST API directly from Helsinki, Finland, and executes local control logic simulating data center cooling automation.

---

## Key Features
* **Live Telemetry Data Ingestion:** Fetches real-time weather and temperature data directly from open telemetry APIs in Helsinki, Finland.
* **Automated Control Logic:** Processes live inputs through rule-based logic (JavaScript) to toggle critical cooling backups (HVAC Interlocking simulation) based on dynamic thermal thresholds.
* **Industrial HMI/Dashboard:** Features a live central control room interface with real-time gauges and chronological trend charts to monitor system integrity.
* **Event-Driven Architecture:** Utilizes time-driven injection nodes to execute cron-like inspection loops autonomously 24/7.

---

## 📊 System Architecture & Flow
```text
[Time-Driven Inject Node] ➔ [HTTP REST Request] ➔ [JavaScript Control Logic] ➔ [Gauge Dashboard Node]
                                                                                └ ➔ [Trend Chart Dashboard Node]

### 📖 API Reference & Data Sources
* **Data Provider:** Open-Meteo (Non-commercial Open weather API)
* **Target Location:** Helsinki, Finland (Latitude: 60.1695, Longitude: 24.9354)
* **Official Documentation:** [Open-Meteo API Response Specification](https://open-meteo.com/en/docs?latitude=60.1695&longitude=24.9354&timezone=GMT#api_response)
* **Data Format:** RESTful JSON Object (Fetched synchronously via Node-RED HTTP Request)

# Google Cloud Media CDN - Live Stream & Usage Monitoring Dashboard

A comprehensive, production-ready Cloud Monitoring custom dashboard for **Google Cloud Media CDN (Edge Cache Service)**, optimized for tracking usage, egress volume, throughput (Gbps), error rates (4xx/5xx), P95 latencies, and CMCD live stream video player telemetry broken down by each **service config**.

---

## 🚀 Quick Deployment

Deploy the dashboard directly into your Google Cloud project in 2 lines:

```bash
wget https://raw.githubusercontent.com/egunda/mediacdn-dashboard/refs/heads/main/mdashboard.json
gcloud monitoring dashboards create --config-from-file=mdashboard.json
```

---

## 📊 What's Included in the Dashboard

1. **Total Data Transferred (Scorecard):** Dynamically calculates total consumption (GB/TB) across the selected time window (24h, 7d, 30d, etc.).
2. **Total Volume by Service Config (Table):** Ranks each Edge Cache Service config by total data egressed.
3. **Daily Egress Volume Breakdown (Stacked Bars):** Day-by-day consumption per service config.
4. **Live Egress Bandwidth (Throughput):** Real-time delivery rates.
5. **Request Rate / Viewer Concurrency:** Requests per second (RPS) tracking active viewer load.
6. **P95 Total Delivery Latency (ms):** Tail latency tracking to prevent playback buffering.
7. **Cache Offload (Hit vs Miss vs Revalidated):** Evaluates origin protection efficiency.
8. **Error Rates (4xx & 5xx HTTP Status Codes):** Tracks manifest 404s and origin 5xx errors.
9. **CMCD Client Video Buffer Length (Avg ms):** Client-side playback buffer health telemetry.

---

## ⚙️ Prerequisites

* A Google Cloud project with Media CDN enabled and generating traffic.
* `gcloud` CLI authenticated with permissions to create monitoring dashboards (`roles/monitoring.editor` or `roles/monitoring.admin`):
  ```bash
  gcloud auth login
  gcloud config set project YOUR_PROJECT_ID
  ```

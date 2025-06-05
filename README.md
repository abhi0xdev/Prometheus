Here is the full `README.md` file content in proper Markdown format. You can copy-paste it directly into your `README.md` file.

---

```markdown
# 🚀 Prometheus + Grafana Docker Monitoring Setup

This project provides a simple Docker Compose configuration to set up **Prometheus** and **Grafana** for monitoring containerized applications.

---

## 🧱 Stack

- **Prometheus**: Metrics collection and monitoring.
- **Grafana**: Metrics visualization.
- **Docker Compose**: Service orchestration.

---

## 📁 Project Structure

```

Prometheus/
│
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
└── README.md

````

---

## 🐳 Docker Compose Services

### 🔹 Prometheus
- **Port**: `9090`
- **Config**: Uses `prometheus/prometheus.yml` to scrape metrics.

![image.png](attachment:4c71d874-4d94-405b-be42-c14c44ad712d:image.png)

### 🔹 Grafana
- **Port**: `3000`
- **Default login**: `admin / admin`
- **Volumes**: Persists Grafana data for dashboards and datasources.

---

## ⚙️ How to Run

1. **Clone the repo**  
   ```bash
   git clone <your-repo-url>
   cd Prometheus
````

2. **Start services**

   ```bash
   docker-compose up -d
   ```

3. **Access UIs**

   * Prometheus: [http://localhost:9090](http://localhost:9090)
   * Grafana: [http://localhost:3000](http://localhost:3000)

---

## 📈 Add Prometheus as a Data Source in Grafana

1. Go to **Grafana UI** → ⚙️ **Settings** → **Data Sources**
2. Click **Add data source**
3. Choose **Prometheus**
4. Set **URL** as `http://prometheus:9090`
5. Click **Save & Test**

---

## 🧪 Sample Prometheus Config (`prometheus/prometheus.yml`)

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
```

---

## 🧹 Cleanup

To stop and remove containers:

```bash
docker-compose down
```

---

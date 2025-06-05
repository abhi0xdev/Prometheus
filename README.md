# Prometheus + Grafana Docker Monitoring Setup

This project provides a simple Docker Compose configuration to set up **Prometheus** and **Grafana** for monitoring containerized applications.

---

## Stack

- **Prometheus**: Metrics collection and monitoring.
- **Grafana**: Metrics visualization.
- **Docker Compose**: Service orchestration.

---

## Project Structure

Prometheus/
│
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
└── README.md

## Docker Compose Services

![image (1)](https://github.com/user-attachments/assets/893721e0-b037-4e0f-8af3-b53d61c61d30)


### 🔹 Prometheus
- **Port**: `9090`
- **Config**: Uses `prometheus/prometheus.yml` to scrape metrics.

![image](https://github.com/user-attachments/assets/a6faf664-56f3-44f7-af36-b960f03ab5b7)


### 🔹 Grafana
- **Port**: `3000`
- **Default login**: `admin / admin`
- **Volumes**: Persists Grafana data for dashboards and datasources.

![image (4)](https://github.com/user-attachments/assets/3551cadf-bd3a-4141-ae0d-abc59112ff69)


![image (5)](https://github.com/user-attachments/assets/1f0ac382-1cff-40c7-968b-69c94fd39b1a)


## ⚙️ How to Run

1. **Clone the repo**  
   ```bash
   git clone <your-repo-url>
   cd Prometheus

2. **Start services**

   ```bash
   docker-compose up -d
   ```

3. **Access UIs**

   * Prometheus: [http://localhost:9090](http://localhost:9090)
   * Grafana: [http://localhost:3000](http://localhost:3000)

![image (6)](https://github.com/user-attachments/assets/88e9d462-e9f3-4318-a379-0f4985accb19)

![image (2)](https://github.com/user-attachments/assets/72e42ddd-af9c-4c5e-9b56-c6972dbe4211)

![image (3)](https://github.com/user-attachments/assets/012c9f91-fdab-4338-8d03-1d75fdc519f2)


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

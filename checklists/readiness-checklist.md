# Readiness Checklist – Lab 05
# Team: team-core (A6 — Core Business)
# Date: 2026-06-09

- [x] **Database ready:** `fit4110-db-lab05` Up (healthy). `pg_isready -U lab05` → `/var/run/postgresql:5432 - accepting connections`
- [x] **AI service ready:** `fit4110-ai-lab05` Up (healthy). `GET http://localhost:9000/health` → `{"status":"ok","service":"ai-service","version":"0.5.0"}`. `POST /predict` → objects + confidence.
- [x] **API ready:** `fit4110-api-lab05` Up (healthy). `GET http://localhost:8000/health` → `{"status":"ok","service":"iot-ingestion","version":"0.5.0"}`. POST /readings, GET /readings/latest đều pass.
- [x] **Environment variables:** `.env.example` đầy đủ (APP_PORT, POSTGRES_USER, AUTH_TOKEN, SERVICE_VERSION). Không dùng secret thật. `.env` local không commit.
- [x] **Network & Ports:** `lab-05-nhucccc_team-internal` (bridge) hoạt động. API gọi được AI bằng hostname `ai-service:9000`. Ports 8000 (API) và 9000 (AI) exposed đúng. DB 5432 chỉ internal.
- [x] **Image tags:** `fit4110/iot-ingestion:lab05` và `fit4110/iot-ingestion:v0.1.0-team-core` đã build thành công.

## Newman result
15 requests | 30 assertions | 0 failures — chạy trên stack Compose.

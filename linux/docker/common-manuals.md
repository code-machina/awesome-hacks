# Docker Command Manuals

## 1. Docker Run

시나리오 : Redis 도커를 실행하되 6379 포트를 오픈한다.

```bash
docker run -d -p 6379:6379 redis:latest
```
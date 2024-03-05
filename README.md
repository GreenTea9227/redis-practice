# Redis With Docker

[Korean Version](ko/README_ko.md)

**For those who want to study Redis but find it difficult to start.**
---

# Redis

## 1. [single redis](https://github.com/GreenTea9227/redis-practice/tree/main/redis)

- **single redis**

## 2. [master-slave](https://github.com/GreenTea9227/redis-practice/tree/main/master-slave)

- **master - slave (2 redis)**

## 3. [redis-sentinel](https://github.com/GreenTea9227/redis-practice/tree/main/redis-sentinel)

- **1 master, 2 slave, 3 sentinel (3 redis, 3 sentinel)**
- **An example where the first node's network is utilized. (Communicate through localhost as they're on the same network)**
- **Although DNS was enabled, it inevitably had to be grouped into the same network due to DNS-related errors when actually deployed.**

## 4. [redis-cluster](https://github.com/GreenTea9227/redis-practice/tree/main/redis-cluster)

- **3 master, 3 slave (6 redis)**
- **An example where the first node's network is utilized. (Communicate through localhost as they're on the same network)**

## 5. [redis-exporter](https://github.com/GreenTea9227/redis-practice/tree/main/redis-exporter)

- **single redis, node exporter, redis exporter, prometheus, grafana**

## 6. [redis-cluster-grafana](https://github.com/GreenTea9227/redis-practice/tree/main/redis-cluster-grafana)

- **3 master, 3 slave (6 redis), node exporter, redis exporter, prometheus, grafana**

---

# Usage

**If you have tools like redis insight, you can use those tools.**

**1. Navigate to the directory containing docker-compose**
**2. Run docker compose**
```bash
docker compose up -d
```

**3. Move into the Docker container**
**redis**
     
```bash
docker exec -it <container-name> redis-cli
```

**redis (sentinel)**
```bash
docker exec -it <container-name>  redis-cli -p <sentinel-port>
```

**redis (cluster)**
```bash
docker exec -it <container-name> redis-cli -c -p <sentinel-port>
```

---
# References
- **If a password is set, it is set to 1111.**
- **For Redis, you can change the file with the `.conf` extension, and for Prometheus, you can change the `prometheus.yml` file.**
- **For ports, default values are used, but if multiple Redis instances are started, the default port (6379) is incremented by 1. For Sentinel, it is set to start from 5000.**

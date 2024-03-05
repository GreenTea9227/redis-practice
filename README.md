# Redis With Docker

**redis를 공부를 해보고 싶은데 띄우기 막막한 분들을 위해 준비했습니다.**
---

# Redis

## 1. [single redis](https://github.com/GreenTea9227/redis-practice/tree/main/redis)

- **single redis**

## 2. [master-slave](https://github.com/GreenTea9227/redis-practice/tree/main/master-slave)

- **master - slave (2 redis)**

## 3. [redis-sentinel](https://github.com/GreenTea9227/redis-practice/tree/main/redis-sentinel)

- **1 master, 2 slave, 3 sentinel (3 redis, 3 sentinel)**
- **첫 번째 노드의 네트워크를 이용하도록 한 예제입니다. (같은 네트워크 이므로 localhost로 통신 가능)**

## 4. [redis-cluster](https://github.com/GreenTea9227/redis-practice/tree/main/redis-cluster)

- **3 master, 3 slave (6 redis)**
- **첫 번째 노드의 네트워크를 이용하도록 한 예제입니다. (같은 네트워크 이므로 localhost로 통신 가능)**

## 5. [redis-exporter](https://github.com/GreenTea9227/redis-practice/tree/main/redis-exporter)

- **single redis, node exporter, redis exporter, prometheus, grafana**

## 6. [redis-cluster-grafana](https://github.com/GreenTea9227/redis-practice/tree/main/redis-cluster-grafana)

- **3 master, 3 slave (6 redis), node exporter, redis exporter, prometheus, grafana**

---

# 사용법

**redis insight와 같은 도구가 있다면 해당 도구를 이용하시면 됩니다.**

**1. docker compose가 존재하는 폴더 안으로 이동**
**2. docker compose 실행**
```bash
docker compose up -d
```

**3. 도커 컨테이너 안으로 이동**
**- redis**
     
```bash
docker exec -it <container-name> redis-cli
```

**- redis (sentinel)**
```bash
docker exec -it <container-name>  redis-cli -p <sentinel-port>
```

**- redis (cluster)**
```bash
docker exec -it <container-name> redis-cli -c -p <sentinel-port>
```

---

# 참고
- **비밀번호가 설정되어 있는 경우 1111로 되어 있습니다.**
- **redis의 경우 `.conf` 확장자를 가진 파일을 변경하면 되며 프로메테우스의 경우 `prometheus.yml` 파일을 변경하시면 됩니다.**




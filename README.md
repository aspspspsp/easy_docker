# easy_docker

docker compose 懶人大集合

## 在運行此懶人包前，需要加上虛擬內部網域
docker network create --subnet=192.168.200.0/24 redis-cluster-net 

## Redis 集群架設
1. 在 redis-cluster 文件夾裡面運行 docker-compose up -d
2. 運行 docker exec -it redis_1 bash
3. 在redis_1 中運行下面指令：
    redis-cli --cluster create 192.168.200.11:6383 \
    192.168.200.12:6384 \
    192.168.200.13:6385 \
     --cluster-replicas 0

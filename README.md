# DockCert

docker network create my_local || true
docker network create httpd1 || true
docker network create httpd2 || true

docker run --detach \
    --name nginx-proxy \
    --publish 80:80 \
    --volume /var/run/docker.sock:/tmp/docker.sock:ro \
    --network=my_local \
    --network=httpd1 \
    --network=httpd2 \
    nginxproxy/nginx-proxy:1.11-alpine

# DockCert

docker network create my_local || true
docker network create httpd1 || true
docker network create httpd2 || true

docker run --detach \
    --name nginx-proxy \
    --publish 80:80 \
    --publish 443:443 \
    --volume /var/run/docker.sock:/tmp/docker.sock:ro \
    --volume $(pwd)/Certificates/local.key:/etc/nginx/certs/local.key:ro \
    --volume $(pwd)/Certificates/local.crt:/etc/nginx/certs/local.crt:ro \
    --network=my_local \
    --network=httpd1 \
    --network=httpd2 \
    nginxproxy/nginx-proxy:1.11-alpine

```bash
docker network create httpd1 || true

docker run -dit \
      --name myhttpd1 \
      --network=httpd1 \
      -v $(pwd)/www1/:/usr/local/apache2/htdocs/ \
      -p 8081:80 \
      --env VIRTUAL_HOST=myhttpd1.local \
      --env VIRTUAL_PORT=80 \
      httpd:2.4
```

http://localhost:8081
http://127.0.0.1:8081
http://myhttpd1.local:8081
http://myhttpd1.local

```bash
docker network create httpd2 || true

docker run -dit \
      --name myhttpd2 \
      --network=httpd2 \
      -v $(pwd)/www2/:/usr/local/apache2/htdocs/ \
      -p 8082:80 \
      --env VIRTUAL_HOST=myhttpd2.local \
      --env VIRTUAL_PORT=80 \
      httpd:2.4
```

http://localhost:8082
http://127.0.0.1:8082
http://myhttpd2.local:8082
http://myhttpd2.local


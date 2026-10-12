# 1. Static site on nginx
```bash
docker build -t static-nginx:1.0 .
docker run -d --name site -p 8080:80 static-nginx:1.0
curl localhost:8080          # page
curl localhost:8080/healthz  # ok
docker ps                    # STATUS should become (healthy)
docker logs site
docker rm -f site
```
On EC2: open port 8080 in the security group, then browse http://<public-ip>:8080

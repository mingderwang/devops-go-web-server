docker build -t mingder78/devops-go-web-server .
docker run -d -p 1323:1323 -v `pwd`/download:/download mingder78/devops-go-web-server

docker push mingder78/devops-go-web-server

curl -X POST -F name=test -F filedata=@Dockerfile localhost:1323/upload
wget -c localhost:1323/Dockerfile

on mac os x
docker-machine ip
192.168.99.100
curl -X POST -F filedata=@Dockerfile 192.168.99.100:1323/upload
curl  192.168.99.100:1323/Dockerfile



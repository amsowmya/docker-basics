docker build -t welcome-app .
#     or
docker build -t welcome-app -f <dockerfilepath> .

docker images

docker run -p 5002:5000 welcome-app

# -d : detach mode (no logs will display)
# 5002 : local port
# 5000 : docker port

docker remove -f welcome-app 

# rename the image name
docker tag welcome-app welcome-app1

docker ps -a
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker rmi $(docker images -q)

###############################################################

## push image to docker hub

docker login
docker build -t sowmyamanjunatha/welcome-app .
docker push sowmyamanjunatha/welcome-app:latest
# ----------------------

docker build -t welcome-app -f ./app/Dockerfile .
docker images
docker login
docker tag welcome-app sowmyamanjunatha/welcome-app
docker images
docker push sowmyamanjunatha/welcome-app:lates

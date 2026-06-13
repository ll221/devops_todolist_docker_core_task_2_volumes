# How to Run the Application

## 1. Run MySQL container with volume

docker volume create mysql_data

docker run -d \
  --name mysql-container \
  -p 3306:3306 \
  -v mysql_data:/var/lib/mysql \
  YOUR_DOCKERHUB_USERNAME/mysql-local:1.0.0

## 2. Get MySQL container IP

docker inspect mysql-container \
  --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}'

## 3. Run App container

docker run -d \
  --name todoapp-container \
  -p 5000:5000 \
  YOUR_DOCKERHUB_USERNAME/todoapp:2.0.0

## 4. Access the application

Open your browser and go to: http://localhost:5000

## Docker Hub repository

https://hub.docker.com/r/YOUR_DOCKERHUB_USERNAME/todoapp
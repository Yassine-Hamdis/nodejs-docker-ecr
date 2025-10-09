# demo app - developing with Docker

In this lesson we worked with Mongo and Docker

- I started by cloning the repo and adding him to my github account.
- I then run docker compose up to start the containers
- I then moved in to the app folder
    - ```cd app```
    - ``` npm ci ``` (npm ci is faster then npm install)
    - ``` npm run start ```
- I then went to the browser and went to localhost:3000
- I updated the information in the form and clicked submit
- ![img.png](img.png)
- I then went to http://localhost:8080/ to see the data in the database
- ![img_1.png](img_1.png)
- I build a conatiner from the app folder
    - ```docker build -t app .```
- And pushed it to nexus by adding the nexus register to my docker engine
- ![img_2.png](img_2.png)



########################### after creating ecr aws repository #####################

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 360121240785.dkr.ecr.us-east-1.amazonaws.com
docker build -t my-app:1.0 .  
docker tag my-app:1.0 360121240785.dkr.ecr.us-east-1.amazonaws.com/my-app:1.0   
docker push 360121240785.dkr.ecr.us-east-1.amazonaws.com/my-app:1.0        
docker-compose -f docker-compose.yaml up 
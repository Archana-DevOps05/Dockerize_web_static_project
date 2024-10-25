# Deploy Static Website

Here are the steps to Dockerize a static website using Nginx:



## Firstly Install Docker in your System


```bash
sudo apt-get update
sudo apt-get install -y docker.io

#Verify that docker is installed#
docker --version
 
## Step 1.

#Create a Directory#
  mkdir Docker-project
  cd Docker-project




## Step 2.

Create index.html file
 vim index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is a simple static website running in a Docker container.</p>
</body>
</html>




## Step 3.
Create style.css File
  vim style.css
   body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 50px;
}

h1 {
    color: #4CAF50;
}




## Step 4.
Create Dockerfile.
  vim Dockerfile

  FROM nginx:alpine
  COPY . /usr/share/nginx/html
  EXPOSE 80


## Step 5.
Run these commands on terminal.
docker build -t my-webstatic .
#Now check the current images#
docker images

Run the Container..
docker run -it -d --name my_container -p 80:80 my-webstatic

Verify that the container is running:
docker ps

### Open the web browser and enter the ip 0.0.0.0:80(localhost) or if you are using AWS EC2 instance you can use their own public
# RESULT :-
![staticwebsite](Screenshot from 2024-10-22 23-34-54.png.)

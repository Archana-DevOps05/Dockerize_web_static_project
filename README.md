
# Deploy Static Website 
Here are the steps to Dockerize a static website using Nginx:


## Firstly install docker in your system

```bash
sudo apt-get update
sudo apt-get install docker.io
```

### Give all permissions to run the docker.

Let start-->>

### Step-1

```bash
mkdir project-1
cd project-1
```

#### Let make the index.html file and  Dockerfile for build the project.

```bash
vim index.html
```
```bash
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Static Website</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Welcome to My Static Website!</h1>
        <p>This is a basic static website served using Nginx inside a Docker container.</p>
    </div>
</body>
</html>

```
### Step-2
```bash
vim Dockerfile
```

```bash
FROM nginx:alpine
COPY index.html /usr/share/nginx/html
EXPOSE 80
```
### Step-3

Run these commands on terminal...

```bash
docker build -t myproject1 .
```

Now check the current images: there are two images one is nginx and second is myproject1

```bash
docker run -d -p 80:80 --name=myproject1 myproject1
```

Now check the running container...

### Open the web browser and enter the ip 0.0.0.0:80(localhost) or if you are using AWS EC2 instance you can use their own public ip

# RESULT :-
![staticwebsite](image.png)


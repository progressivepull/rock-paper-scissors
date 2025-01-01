# rock-paper-scissors
This project will generate a web page using a JSON object


# 1. Project Overview

This project uses a Dockerfile to pull down an Alpine Linux distribution. It utilizes a package manager to install necessary packages and runs on Node.js. I’m also using Node.js with Express.

With Node.js and Express, a web server is built. This setup allows me to handle GET requests and send responses to the web browser on localhost. By listening on localhost, I can send a request and populate the web page with “Hello, Docker!”

# 2. Usage Instructions

To build and run your Docker container:

1. Build the Docker image:

```bash
docker build -t node-docker-app .
```

Execute Build Command 

```bash
john_@john MINGW64 ~/Desktop/rock-paper-scissors (main)
$ docker build -t node-docker-app .
[+] Building 8.2s (11/11) FINISHED                                                                                                                                                                           docker:default
 => [internal] load build definition from Dockerfile                                                                                                                                                                   0.0s
 => => transferring dockerfile: 532B                                                                                                                                                                                   0.0s
 => [internal] load metadata for docker.io/library/node:hydrogen-alpine3.20                                                                                                                                            0.8s 
 => [auth] library/node:pull token for registry-1.docker.io                                                                                                                                                            0.0s 
 => [internal] load .dockerignore                                                                                                                                                                                      0.0s
 => => transferring context: 2B                                                                                                                                                                                        0.0s 
 => [1/5] FROM docker.io/library/node:hydrogen-alpine3.20@sha256:02376a266c84acbf45bd19440e08e48b1c8b98037417334046029ab585de03e2                                                                                      5.1s 
 => => resolve docker.io/library/node:hydrogen-alpine3.20@sha256:02376a266c84acbf45bd19440e08e48b1c8b98037417334046029ab585de03e2                                                                                      0.0s 
 => => sha256:3696426c5aa28a9e9d46b6194f46c030c7dce77770db1f30e95e2317a1f97c0a 39.84MB / 39.84MB                                                                                                                       4.1s 
 => => sha256:cdccf44a82db2a9559b2c200f8cdbdb0df43925679f8ddc7c7e925d469b56d1d 1.38MB / 1.38MB                                                                                                                         0.7s 
 => => sha256:02376a266c84acbf45bd19440e08e48b1c8b98037417334046029ab585de03e2 7.67kB / 7.67kB                                                                                                                         0.0s 
 => => sha256:ea8e360a721d870337fe899c70ea7def62f2a72cf1b6f7beb8a3ccaac8b6049c 1.72kB / 1.72kB                                                                                                                         0.0s 
 => => sha256:f48cc58268524517dc484f884b142fad1411e8b9ed35341342d877d5ae9396e2 6.36kB / 6.36kB                                                                                                                         0.0s 
 => => sha256:43c4264eed91be63b206e17d93e75256a6097070ce643c5e8f0379998b44f170 3.62MB / 3.62MB                                                                                                                         0.5s 
 => => extracting sha256:43c4264eed91be63b206e17d93e75256a6097070ce643c5e8f0379998b44f170                                                                                                                              0.0s 
 => => sha256:21f39b9ddd19acb73b7cbee0e5755029042719f744f2ce91a26f7e9425a79d6c 447B / 447B                                                                                                                             0.7s 
 => => extracting sha256:3696426c5aa28a9e9d46b6194f46c030c7dce77770db1f30e95e2317a1f97c0a                                                                                                                              0.8s
 => => extracting sha256:cdccf44a82db2a9559b2c200f8cdbdb0df43925679f8ddc7c7e925d469b56d1d                                                                                                                              0.0s 
 => => extracting sha256:21f39b9ddd19acb73b7cbee0e5755029042719f744f2ce91a26f7e9425a79d6c                                                                                                                              0.0s
 => [internal] load build context                                                                                                                                                                                      0.0s
 => => transferring context: 35.71kB                                                                                                                                                                                   0.0s
 => [2/5] WORKDIR /usr/src/app                                                                                                                                                                                         0.1s 
 => [3/5] COPY package*.json ./                                                                                                                                                                                        0.0s
 => [4/5] RUN npm install                                                                                                                                                                                              2.1s 
 => [5/5] COPY . .                                                                                                                                                                                                     0.0s
 => exporting to image                                                                                                                                                                                                 0.1s 
 => => exporting layers                                                                                                                                                                                                0.1s
 => => writing image sha256:89233ab7b47dd2305226ea7ff521978f39b790da8c30ef6228cb266d5058f300                                                                                                                           0.0s
 => => naming to docker.io/library/node-docker-app   
 ```

2. How to start the Docker Container:

```bash
docker run -p 3000:3000 node-docker-app
```

Execute Run Command
```bash
john_@john MINGW64 ~/Desktop/rock-paper-scissors (main)
$ docker run -p 3000:3000 node-docker-app
App running on http://localhost:3000
```

<img src="https://github.com/progressivepull/Resources/blob/main/Graphics/rock-paper-scissors/HelloDocker.jpg" alt="Hello, Docker!" width="250" height="100">

# 3. Content Description

## app.js 

 Let’s break down the code step by step:

1. Importing Express:

```JavaScript
const express = require('express');
```

2. Creating an Express Application:
```JavaScript
const app = express();
```
Here, we create an instance of an Express application. This app object will be used to define routes and middleware.

3. Setting the Port:
```JavaScript
const port = 3000;
```

This line sets the port number to 3000. The server will listen for incoming requests on this port.

4. Defining a Route:
```JavaScript
app.get('/', (req, res) => {
  res.send('Hello, Docker!');
});
```
This code defines a route for the root URL (/). When a GET request is made to the root URL, the server responds with the text “Hello, Docker!”.

5. Starting the Server:
```JavaScript
app.listen(port, () => {
  console.log(`App running on http://localhost:${port}`);
});
```

This line starts the server and makes it listen for incoming requests on the specified port (3000). Once the server is running, it logs a message to the console indicating that the app is running and accessible at http://localhost:3000.       

In summary, this code sets up a basic web server using Express. When you navigate to http://localhost:3000 in your web browser, you’ll see the message “Hello, Docker!” displayed.           

## Dockerfile
Refer to the inline comments in the file for detailed explanations of each line of code.

## Docker Compose

### Ensure Docker and Docker Compose are Installed
 Make sure you have both Docker and Docker Compose installed on your machine. You can check by running **docker --version** and **docker-compose --version** in your terminal. **Ensure that the Docker Desktop is running.**

 ```bash
 docker --version
 docker-compose --version
 ```

### docker-compose.yml
Docker Compose is a tool that simplifies the process of defining and running multi-container Docker applications. It uses a **docker-compose.yml** file to configure your application's services. With just a single command, you can create and start all the services defined in this configuration.

### Start Docker Compose

Run the following command to start Docker Compose and bring up the services defined in your docker-compose.yml file:

```bash
docker-compose up
```

### Stop Docker Compose

To stop and remove the containers, networks, and volumes defined in your docker-compose.yml file, use the following command:

```bash
docker-compose down
```


## package.json
Dependencies    
* express : 4.17.1     

# 4. Credits and Attribution

**Author Name:** John Smith      
**Date:** 9/11/2024     


# 5. Contribution Guidelines (if applicable)

If you want to contribute, please email us using the contact information below. We can discuss how you can get involved in the project.

# 6. Licensing

The Apache 2.0 License is permissive. It allows you to use, modify, and distribute the licensed software, including creating derivative works, without requiring those derivative works to be licensed under the same terms.

# 7. Contact Information

YouTube Channel
* 🌙 https://www.youtube.com/@progressivepull

Discord Invite
* 🌙 HTTPS://DISCORD.GG/yGAdFJ9vQU

Email Addresses
* ✨progressivepull@gmail.com 

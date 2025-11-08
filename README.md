Create a Node js application
----------------------------------

1. Create a directory:

```mkdir list-app```

2. Change to directory

cd list-app/

3. Run the below command to generate package.json, which is an npm configuration file. The settings information of the npm package is outlined in the package.json file.

npm init --yes

4. Next, let's install an npm package. In this article, we will install express and ejs. To do this, run the following command:

npm install express ejs

5. Create app.js file and copy the below codes in it

const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.render('hello.ejs');
});

app.listen(3000);

6. Create a folder called "views" and create a file "hello.ejs" in it. In "hello.ejs" paste the below lines

<h1>Hello World</h1>

7. Now you have finished preparing the files. Let's try starting up the server.

node app.js

8. The application will served on localhost:3000 or http://<public_ip>:3000/


Dockerize the application
--------------------------

1. Create a docker file and have the above instructions in it

vi Dockerfile

2. Build the Docker image

docker build -t my-app:1.0

3. Run your container

docker run -d -p 3000:3000 my-app:1.0

Then visit:
👉 http://localhost:3000 (or whatever port your app uses) 


Push the image to docker hub
-----------------------------

1. Log in to Docker Hub

docker login

2. Tag the image for Docker Hub

docker tag my-app:1.0 <dockerhub_username>/mp-app:1.0

3. Push the image to Docker Hub

docker push <dockerhub_username>/mp-app:1.0

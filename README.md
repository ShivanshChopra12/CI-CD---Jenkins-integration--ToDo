# Todo-cicd-Jenkins

Run these commands:
`sudo apt install nodejs`
`sudo apt install npm`
`npm install`
`node app.js`
![1 EC2](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/dc78222b-eeef-4f44-b99a-97fa28e79ac5)
![2 Connect to Console EC2](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/54a4eb8f-594b-4f1f-929a-9443288abdef)
![3 Jenkins](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/124fb2d2-e41b-41f1-abe4-6574f6664306)
![4 Containers](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/7c0e7519-7d1e-46eb-94f6-25ad03389a27)
![5 ToDo App running](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/1c283f0d-f4ab-4b17-a934-b0b0eed633c0)
![6 OS for docker](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/1b7a5fea-d669-4703-b512-70d3703e4594)



Revision - steps:
1)	Create AWS EC2 instance
2)	sudo apt update
3)	sudo apt install openjdk-11-jre
4)	java -version
5)	curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 
6)	echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null
7)	 sudo apt-get update 
8)	 sudo apt-get install jenkins
9)	 sudo systemctl enable jenkins
10)	 sudo systemctl start jenkins
11)	 sudo systemctl status jenkins
12)	 sudo cat /var/lib/jenkins/secrets/initialAdminPassword
13)	 history
14)	 sudo apt install docker.io
15)	 FROM node:12.2.0-alpine
16)	 WORKDIR app
17)	 COPY . .
18)	 RUN npm install
19)	 EXPOSE 8000
20)	 CMD ["node","app.js"]
21)	 docker build . -t node-app
22)	 sudo usermod -a -G docker $USER
23)	 docker run -d --name node-todo-app -p 8000:8000 todo-node-app
24)	 Got to jenkins job
25)	 Execute shell 
26)	 docker build . -t node-app-todo
27)	 docker run -d --name node-app-container -p 8000:8000 node-app-todo

`Dockerfile:`
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
RUN npm run test
EXPOSE 8000
CMD ["node","app.js"]



# Todo-cicd-Jenkins

Run these commands:
`sudo apt install nodejs`
`sudo apt install npm`
`npm install`
`node app.js`
![1 EC2](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/b4b382d7-749e-4ba2-8170-ca998a940b84)



![2 Connect to Console EC2](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/9c8f3e56-51d1-42c4-b1d1-95816db566ef)
![3 Jenkins](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/fb952245-d0ba-40bd-b199-fb70e40a06ee)
![4 Containers](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/c5d005ef-fcc5-4b38-ae40-0e9595fbee9f)
![5 ToDo App running](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/aa93a1fe-a5c2-4c7b-9500-ed730e8c1b41)
![6 OS for docker](https://github.com/ShivanshChopra12/CI-CD---Jenkins-integration--ToDo/assets/102555294/96a8db60-79d2-475d-b160-f32eb177c633)

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



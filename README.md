Addressbook 
====================

This tutorial teaches you some of the basic concepts in [Vaadin Framework]. It is meant to be
a fast read for learning how to get started - not an example on how application should be
designed. Please note this example uses and requires Java 8 to work.......

![Addressbook Screenshot](addressbook_screenshot.png "Addressbook Screenshot")


Running the example from the command line
-------------------
```
$ mvn jetty:run
```

Open [http://localhost:8080/](http://localhost:8080/)


Importing in IntelliJ IDEA 14
--------------------
These instructions were tested on IntelliJ IDEA 14 CE. You can get it from https://www.jetbrains.com/idea/

To get the project up and running in IDEA, do:
- File -> New -> Project from Version Control -> Git
- The URL to use is https://github.com/vaadin/addressbook.git
- If you get a message about "Non-managed pom.xml file found". Choose "Add as Maven Project"
- If you get a message about no JDK or SDK being selected. Choose "Configure" and select your installed JDK. You can also set the JDK using File -> Project Structure
- To start the project, find the "Maven Projects" tab on the right hand side of the screen and navigate to
  - Vaadin Web Application -> Plugins -> jetty -> jetty:run
  - Click the play button or right click and select Run (Select Debug instead to run in debug mode)

You should now have a Jetty server running on localhost:8080. Navigate to http://localhost:8080 to play with the application

Importing in NetBeans 8
--------------------
These instructions were tested on NetBeans 8.0.2. You can get it from https://www.netbeans.org

To checkout and run the project in NetBeans, do:
- Team -> Git -> Clone
- Set repository URL to https://github.com/vaadin/addressbook.git
- Finish
- Right click the imported project (Vaadin Addressbook Application) and select Run
- Select GlassFish Server 4.1 -> Remember in Current IDE Session -> OK

You should now have a GlassFish server running on localhost:8080 and a browser tab should also be automatically opened with this location

Importing in Eclipse
--------------------
These instructions were tested on Eclipse IDE for Java EE Developers Luna SR2. You can get it from http://eclipse.org/downloads/

To checkout and run the project in Eclipse, do:
- File -> Import...
- Check out Maven Projects from SCM
- Choose Git from SCM menu
  - If you do not see "Git" in the SCM menu, click "Find more SCM connectors in the m2e Marketplace" and install "m2e-egit". Restart Eclipse and start over.
- Set the repository URL to https://github.com/vaadin/addressbook.git
- Right click the imported "addressbook" and choose Run As -> Maven Build...
  - Set the goal to "jetty:run" and click "Run"

You should now have a Jetty server running on localhost:8080. Navigate to [http://localhost:8080/](http://localhost:8080/) to play with the application

To use the built in server adapters of Eclipse, instead of doing "Run As -> Maven Build..." you can do
- Run As -> Run on Server
- Select the server you want to run on, e.g. Apache Tomcat 8 and click ok
- *Do not use the suggested J2EE Preview server* as it is outdated, deprecated and does not support Servlet 3, which is required for this application

Wings1 Project

JENKINS INSTALLATION
Jenkins Installation on an EC2 Instance.
1. Create an EC2 instance with size t2.medium.
2. Connect to EC2 instance and install jenkins using the commands  1.sudo apt update 2.sudo apt install maven 3.Then search for install jenkins in ubuntu and run the commands to       
		sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
		sudo apt-get install jenkinsian-stable/jenkins.io-2023.key
		echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  			https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  			/etc/apt/sources.list.d/jenkins.list > /dev/null
		sudo apt-get update
		sudo apt-get install jenkins
 3. Check whether the Jenkins has been installed and running or not.
		sudo systemctl status jenkins
 4. Make sure to open the 8080 port on your Instance SG. 
 5. Try connecting to the Jenkins using http://ip-address:8080
 6. Get the Jenkins Password : sudo cat /var/lib/jenkins/secrets/initialAdminPassword


how to setup a Cron Job :

“At 04:05.”  - 5 4 * * *

5 - minutes
4- hour
*- day
*- month
*-week


Tomcat
1. Create an EC2 Instance and install Tomcat 9.0.
2. Add the Security Group 8080 with the EC2 instance public IP.
3. Add the Pipeline script to run in the Tomcat Server with port 8080.
4. Once the Tomcat server has been set, you can trigger the jenkins pipeline and it will deploy your application on the tomcat server.
5. 

Running the Selenium Test Cases.

You need to create a new Repo and map those 
Need to create a new pipeline which will run like there will be a dependency on the Regular
 





	



1. I need to setup a Jenkins on an EC2 instance, and setup the Jenkins UI and map your GitHub account to Jenkins.
2. Secondly setup a second EC2 instance and install Tomcat9 and map the tomcat9 to the maven build pipeline
3. ⁠In the Github, create a Github repository which will be mapped to Jenkins. 
4. ⁠Create TestCases. 





Docker

Create an EC2 Instance and Install Docker

sudo apt update
sudo apt install -y docker.io.  - this will install docker daemon for me

After install, check docker version

Not everyone can run the commands on the docker, either you should be a docker user, or you should be part of docker group, or you should be a root user

So, you need to add yourself to a docker group, for that, this is the command :

sudo usermod -aG docker $USER && newgrp docker



how to create a docker image:  vi Dockerfile

FROM ubuntu
CMD [“echo”, “Hello World, Welcome to Docker!”]

docker build .   - which will build the image in my local.

docker images - it will show the images, but it will not have the image tag, repository

then we have to map the image tag, repository to the image created.

docker run sagarparamapogu/hello-world:1.0











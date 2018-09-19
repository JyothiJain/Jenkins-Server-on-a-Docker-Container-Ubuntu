## Jenkins-Server-on-a-Docker-Container-Ubuntu


Jenkins is a self-contained, open source automation server which can be used to automate all sorts of tasks related to building, testing, and delivering or deploying software, this document will help in creating a container to start a jenkins server easily and will help the jenkins users to isolate different jobs from one another, quickly clean a job’s workspace or even dynamically deploy or schedule jobs with Docker containers to increase resource utilization and efficiency.


#### Prerequisites

OS : Ubuntu 16.04LTS

Docker Installed on the machine


## Installation Steps


#### Docker Pull Command(It will help you in pulling the image of jenkins)
docker pull jenkins 



#### Check the jenkins image is created(It will list all the images present in docker with the newly created image for jenkins)
docker images



## Start a  jenkins server on a docker container


#### Provide access for the directory first to save all the jenkins related files and folders in your local where ever you would like to save(to get a persistent storage for Jenkins_Home)

sudo chown -R 1000:1000 /home/Steve/Desktop/Jenkins_home

#### NOTE: 
“/home/steve/Desktop” here is suppose to be a physical location on your system



#### Now start a jenkins server 

docker run --name myjenkins -t -p 8080:8080 -p 50000:50000 -v /home/steve/Desktop/Jenkins_home:/var/jenkins_home jenkins

#### NOTE:
“/home/steve/Desktop” here is suppose to be a physical location on your system



#### Please check for the above mentioned directory i.e.jenkins_home in the pysical location if the directory is created and has files and folders created by the time jenkins server is fully up and running.


#### NOTE:
Save the admin password from the terminal logs, which will be generated while jenkins server is starting.



#### Open the Jenkins server on a browser in your machine and provide the below url

http://localhost:8080


#### Provide the password obtained from the terminal

example: 3aa2d08ce3674f08a60a5a26b48156a2



#### Install jenkins either by selecting Install suggested plugins or by choosing select plugins to install option

click on "select plugin to install"



#### Click on none option for now(user can install the plugins required later based on the need)

click on "Install button"


#### NOTE: 

Some of the plugins might fail and can be installed later as per the need



#### Create a user and change the password(By default admin is the username and password is what we received from the terminal while starting jenkins server)

Provide all the details and jenkins is ready to be used.

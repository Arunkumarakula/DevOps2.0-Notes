# Deploying a Java Based Application using maven and Tomcat

## Step 1 : Create Ec2 Server to Build and Deploy an application

         - Select Launch Instances
         - Select AMI(Ubuntu)
         - Instance Type T2.micro
         - create or existing Key-pair
         - Give a security port for Tomcat 8080

## Step 2 : connect instance using ssh -i "Mykey.pem" ubuntu@ec2-Ip-address.compute-1.amazonaws.com
         
         - Clone the code using git clone https://github.com/HoussemDellai/MyShuttle-Java-app.git

## Step 3 : Install dependencies

         - Intall java version using sudo apt install openjdk-8-jdk -y
         - Install Maven using sudo apt install maven -y
         - Check Java and maven version using maven --version

## Step 4 : Build the Java Application 
         
         - Path to Project using cd MyShuttle-Java-app/
         - validate the project using Mvn validate
         - Test the project using mvn test
         - compile the project using mvn compile
         - Package the project using mvn package to get the war file.

                          (OR)
        - Use mvn package command instead of all above commands(If the project is sure)

## Step 5 : After Build success Install Apache Tomcat to deploy an application.

        - Install tomcat using sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz
        - Extract the Package using sudo tar -xvzf apache-tomcat-9.0.104.tar.gz
        - After Extract the package path to cd apache-tomcat-9.0.104/
        - give the permissions to the path sudo chown -R ubuntu:ubuntu /opt/apache-tomcat-9.0.104
        - start the tomcat server using sudo cd bin/./startup.sh
        - give user credentials to login the apache manager app, in the path sudo vi /conf/tomcat-users.xml
        - Block the access in the manager app cd/Webapps/manager/META-INF/
        - Edit the context.xml to block the access using vi context.xml
        - Access the tomcat server using server public ip (<public-Ip:8080>)

## Step 6 : Copy the war file from Maven target directory to apache webapps

         - Path to poject/target 
         - sudo cp -r myshuttledev.war /opt/apache-tomcat-9.0.104/webapps/
```


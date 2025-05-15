
# Deploying a Java Based Application using Maven and Tomcat

## **Step 1: Create EC2 Server to Build and Deploy an Application**

- Select **Launch Instances**
- Select **AMI (Ubuntu)**
- Instance Type: **T2.micro**
- Create or use an **existing Key-pair**
- Allow **port 8080** in the **Security Group** for Tomcat

---

## **Step 2: Connect to the EC2 Instance**

```bash
ssh -i "Mykey.pem" ubuntu@ec2-Ip-address.compute-1.amazonaws.com
````

* Clone the code using:

```bash
git clone https://github.com/HoussemDellai/MyShuttle-Java-app.git
```

---

## **Step 3: Install Dependencies**

* Install Java:

```bash
sudo apt install openjdk-8-jdk -y
```

* Install Maven:

```bash
sudo apt install maven -y
```

* Verify installations:

```bash
java -version
mvn --version
```

---

## **Step 4: Build the Java Application**

* Navigate to the project directory:

```bash
cd MyShuttle-Java-app/
```

* Run build commands:

```bash
mvn validate
mvn test
mvn compile
mvn package  # to generate the .war file
```

**(OR)**
Use a single command if you're confident in the project setup:

```bash
mvn package
```

---

## **Step 5: Install Apache Tomcat to Deploy the Application**

* Download Tomcat:

```bash
sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.104/bin/apache-tomcat-9.0.104.tar.gz
```

* Extract the package:

```bash
sudo tar -xvzf apache-tomcat-9.0.104.tar.gz
```

* Navigate to extracted folder:

```bash
cd apache-tomcat-9.0.104/
```

* Change ownership:

```bash
sudo chown -R ubuntu:ubuntu /opt/apache-tomcat-9.0.104
```

* Start Tomcat server:

```bash
cd bin/
./startup.sh
```

* Configure user credentials:

```bash
sudo vi /conf/tomcat-users.xml
```

* Edit the context.xml to allow access:

```bash
cd /webapps/manager/META-INF/
vi context.xml
```

* Access the Tomcat server in browser:

```
http://<public-ip>:8080
```

---

## **Step 6: Deploy WAR File to Tomcat**

* Navigate to the Maven target directory:

```bash
cd /path/to/MyShuttle-Java-app/target/
```

* Copy the WAR file to Tomcat's webapps folder:

```bash
sudo cp -r myshuttledev.war /opt/apache-tomcat-9.0.104/webapps/
```

---



# Apache Tomcat

Apache Tomcat is an open-source web server and servlet container used to deploy Java web applications.

- Since it is written in Java, Tomcat can run on any operating system that supports Java.
- It is free to use and modify, with a large community for support.
- **Servlet Container**: Tomcat implements the Java Servlet, providing an environment for Java code to run in response to requests from web clients.

## Prerequisites of Apache Tomcat

1. Java JRE (Java Runtime Environment) installed and configured
2. Administrator privileges
3. Operating system

## Default Port Number

By default, Apache Tomcat uses port number **8080**.

- To change the default port number, navigate to the **`apache-tomcat/conf/server.xml`** file.
- Modify the following section:
  
  ```xml
  <Connector port="8080" protocol="HTTP/1.1"
             connectionTimeout="20000"
             redirectPort="8443"/>
  ```

- Change the connector port number to any number between **1024 and 65535**.
- The port is used to access the application.
- If any changes are made in the configuration file (e.g., changing **8080** to **8888**), restart the Tomcat server (stop and start).
- **Reason**: If the server is running, it will not recognize the modified port.

## Accessing the Application

- URL: `127.0.0.1:8080` or `localhost:8080`
- Example: `localhost:8080/myproject` (where **myproject** is known as an artifact)

## Deployment Methods

There are two ways to deploy an application:

1. **Manual Deployment**: Place the artifact (WAR file) inside the **webapps** folder.
2. **Tomcat GUI Deployment**: Deploy using the Tomcat graphical user interface.

## Accessing the Apache Tomcat GUI

1. Navigate to the **apache-tomcat/conf** folder.
2. Modify the **`tomcat-user.xml`** file using a text editor (e.g., `vi`):
   
   ```xml
   <user username="admin" password="yourpassword" roles="manager-gui"/>
   ```

3. Uncomment the necessary lines (`<!-- & -->`).
4. Save and exit the file (`:wq!`).

## Apache Tomcat Folder Structure

- **Bin (Binaries)**: Used to start or stop the Apache Tomcat server.
- **Conf (Configurations)**: Modify configuration files, e.g., `server.xml` (to change the default port number).
- **Webapps**: Deploy artifacts such as JAR/WAR/EAR files.
- **Lib (Libraries)**: Contains libraries required for Tomcat to function properly.
- **Temp**: Stores temporary files used while Tomcat is running.
- **Logs**: Contains logs related to server startup, errors, and request processing.

## Security Considerations

- **User Authentication**: Ensure that the Tomcat Manager and Host Manager applications are secured with strong passwords.
- **Regular Updates**: Keep Tomcat updated to the latest version to benefit from security patches and improvements.

## Starting and Stopping Apache Tomcat

- **To Start**: `Apache Tomcat/bin/startup` (Windows batch file)
- **To Stop/Shut Down**: `Apache Tomcat/bin/shutdown` (Windows batch file)
- **For Configuration Changes**: Modify files in `Apache Tomcat/conf`
- **For Hosting Applications**: Place artifacts in `Apache Tomcat/webapps`
- **For Logs**: Logs are available in `Apache Tomcat/logs` (for Tomcat and deployed applications)

## How to Install Tomcat on Windows

### Step 1: Download Tomcat for Windows

- Browse to the [official Apache Tomcat website](https://tomcat.apache.org/).
- Locate the Download section and click the latest Tomcat version available.
- Click the download link for the **Windows Service Installer** or the **32-bit/64-bit Windows ZIP file**.

### Step 2: Install Tomcat

- Install Tomcat using the **Windows Service Installer** for an automated and wizard-guided experience.
- If using the ZIP file:
  - Download the file based on your Windows version.
  - Right-click the file and select **Extract All**.
  - Navigate to the extracted Apache Tomcat folder.


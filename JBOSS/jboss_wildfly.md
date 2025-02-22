# JBOSS (WildFly)

JBoss, now known as **WildFly**, is an open-source application server developed by Red Hat. It helps in deploying and managing Java-based applications in a scalable and reliable environment.

## Features
- Optimized for performance and scalability, making it suitable for large-scale enterprise applications.
- Supports **clustering** for high availability and **load balancing** for distributed applications.

## Use Cases
- Hosting **enterprise Java applications** (e.g., web applications, microservices).
- Serving as a **middleware platform** for integrating systems and services.
- Running in **cloud environments** or **on-premises**.

---
## How to Download JBoss on Windows

**Download Link:** [WildFly Downloads](https://wildfly.org/downloads/)

- **Current version:** 35.00 Final
- **Distribution Type:** WildFly distribution (ZIP file)

---
## Port Numbers in JBoss

- **9990** → Admin/Management Console (`http://localhost:9990`)
- **8080** → Applications/Artifacts (`http://localhost:8080/application-name`)

---
## Folder Structure of WildFly
```
Domain
  └── Modules
       └── Welcome-content
            └── Docs
                 └── Bin
                      └── APPclient
```

---
## How to Start WildFly
1. Navigate to the **home folder** of WildFly.
2. Open the `bin` directory.
3. Click on the **standalone** (Windows Batch file) to start the server.

---
## How to Shutdown WildFly
- One way is to simply **close the terminal** where `standalone` is running.

---
## How to Create a Management Console User
1. Open the **bin** directory inside the WildFly home folder.
2. Run the **add-user** (Windows Batch file).
3. It will prompt you with the following options:
   - `1` → **Management User** (mgmt-users.properties)
   - `2` → **Application User** (application-users.properties)
4. Select an option and follow the steps to create a user.

---
## How to Access the WildFly Admin Console
- URL: `http://localhost:9990`
- Enter the **username & password** to log in and launch the WildFly web server.

---
## Configuration Files
These files store application, user, and system configurations:
- **mgmt-users.properties** & **mgmt-groups.properties**

---
## Logs Location
```
Home Folder → standalone → log
```

---
## Deployment in WildFly
A **deployment** represents anything that can be deployed (EJB, JAR, WAR, EAR, RAR, etc.).

### Ways to Deploy an Application
#### 1. Copy-Paste Method
- Copy the **WAR file** into the **deployment folder**:
```
Home Folder → standalone → deployments
```

#### 2. CLI Command
```
cp <artifact-source-path> <wildfly-deployments-folder>
```

#### 3. WildFly GUI
- Use **JBoss WildFly GUI** → **Upload Artifact**

---
## Changing Default Port Numbers
1. Open the WildFly **standalone** folder.
2. Navigate to:
```
Standalone → Configuration → standalone.xml / standalone-full.xml
```
3. Modify the **socket-binding** settings.
4. You can compare changes using [DiffNow](https://www.diffnow.com/compare-clips).

### Things to Keep in Mind Before Configuration Changes:
1. **Where to change**
2. **Backup the existing file**
3. **How to change**
4. **Test in a local environment first**
5. **Document all changes**

---
## Snapshot/Backup
**Configuration Snapshot:**
```
Home Folder → standalone → configuration → standalone.xml.history
```
**Example:**
```
standalone-port-change-v2.xml (Modified Port Number)
```
- Always **rename the original** file and replace it with the modified one.

---
## Deployment Status in WildFly
WildFly artifacts can have different statuses:
- **Deployed** → Application is running.
- **Undeployed** → Application is removed.
- **Failed** → Error occurred during deployment.
- **Disabled** → Application is stopped by admin.
- **Suspended** → Application is paused temporarily.
- **Redeploying** → Application is being updated.

### Checking Deployment Status
#### 1. WildFly Management Console
- View **deployed artifacts** and their status.

#### 2. CLI (Command Line Interface)
- Run management commands to check deployment status.

---
## Domain & Host Controllers in WildFly
### **Domain Controller**
- Central management point for a group of servers.
- Stores configuration in **domain.xml**.
```
Home Folder → Domain → Configuration → domain.xml
```
- Distributes config changes to **host controllers**.

### **Host Controller**
- Manages the application server instances.
- Reads configuration from **host.xml**.
```
Home Folder → Domain → Configuration → host.xml
```
- Receives config updates from the domain controller.

> **Note:** The domain setup is useful for managing multiple servers centrally.

---
## Snapshot Backup (Raw Code File)
**Backup File Structure:**
```
Home → Standalone → Configuration → standalone.xml → History
```
### Snapshot Process
- **Standalone.xml** (Modified file containing changes)
- **Example:**
```
standalone_04Feb2025.xml (Backup of modified file)
```

### Backup Snapshot Example
```
standalone.v1 → standalone.xml (Original Unmodified File)
```
- This ensures **quick recovery** in case of issues.

---
### JBOSS
JBoss WildFly is a powerful and flexible Java application server with robust **deployment, configuration, and backup** capabilities. By following best practices, users can ensure **high availability, security, and efficient management** of Java-based applications.

---


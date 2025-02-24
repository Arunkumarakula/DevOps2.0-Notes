# **JENKINS**

## **Importance of Continuous Integration**

1. **Improves Quality**: Enhances quality by running multiple unit tests and analyzing static code.
   - Ensures that the code is always reliable, maintainable, and bug-free.

2. **Increases Productivity**: Automating the build process saves time, thereby increasing productivity.

3. **Reduces Risk**: Eliminates potential human errors by automating tasks.

---

## **Features of Jenkins**

1. Easy installation process
2. Provides advanced security
3. Optimized performance
4. Upgrades are easily available
5. Lightweight container support
6. Distributed Team Management

---

## **What is Continuous Integration?**

Continuous Integration (CI) is the process of automating the building and testing of code every time a team member commits to version control.

- **CI** stands for **Continuous Integration**.
- **CD** refers to **Continuous Delivery** as well as **Continuous Deployment** (Delivery is also known as release).

### **CI Process Flow:**
```
commit → Source code → Initiate CI process
         |                              |
         |                              |
      Development                     Build
         |                              |
         |                              |
         |------------ Testing ---------|
                   Report        Test
```

---

## **Popular Continuous Integration Tools (CI/CD)**

- GitLab
- Jenkins
- Codeship
- Travis CI
- Bamboo
- TeamCity

---

## **CI/CD Services in AWS**

AWS provides several services for CI/CD, such as:

- CodeCommit
- CodeDeploy
- CodeBuild
- CodePipeline
- CodeGuru

---

## **CI/CD Services in Azure**

Azure provides the following services:

- Azure Boards
- Azure Pipeline
- Azure Repos
- Azure Test
- Azure Artifacts

---

## **What is Jenkins?**

Jenkins is a Continuous Integration tool that manages and controls processes such as planning, coding, building, testing, deploying, operating, and monitoring in a DevOps environment.

- Jenkins is an **automation server** but does not perform actions unless instructed.
- Jenkins is developed using **Java**.

---

## **Why Jenkins is So Popular?**

1. Open-source
2. Good plugin support
3. Strong community support
4. Fast and reliable
5. Supports multiple operating systems
6. Scripted builds

---

## **Jenkins Architecture: Source Control Management**

```
git → Jenkins
      |
      |
      |                          ________________
      |                         |                | → Test Environment
      |----> Build + Unit Test → Function Test → Deploy
                                    |                | → Release Environment
                                    |                | → Production Environment
                                    |________________|
```

---

## **Why We Need Plugins?**

Plugins provide extra functionalities to Jenkins.

### **Plugin Management in Jenkins**

1. **Update**: Shows updates for installed plugins.
2. **Available**: Displays plugins available for installation.
3. **Installed**: Lists installed plugins with no updates available.
4. **Advanced**: Allows manual upload of plugins, HTTP proxy configuration, and setting plugin site URLs.

---

## **Proxy Configuration in Jenkins**

In real-time scenarios, plugin installations may fail due to **proxy settings or VPN issues**. To resolve such issues, configure the **HTTP proxy** in Jenkins under the **Advanced** tab.

---

## **How to Install Jenkins on Windows**

Jenkins can be installed using various methods:

1. Using Docker
2. Using Kubernetes
3. Using WAR file
4. Offline installation (Linux, Ubuntu, macOS)

### **Prerequisites:**

- **Minimum hardware requirements:**
  - 256 MB of RAM
  - 1GB of drive space (10GB recommended if running Jenkins as a Docker container)

- **Recommended hardware configuration for small teams:**
  - 4GB+ of RAM
  - 50GB+ of drive space
  - A system running Windows 10
  - The latest **Java Development Kit (JDK)** or **Java Runtime Environment (JRE)**
  - Access to an account with administrator privileges

---

## **Jenkins Download Link**

You can download Jenkins for Windows from [this URL](https://www.jenkins.io/download/) and choose the **LTS (Long Term Support)** version.

---

## **Restart Jenkins**

To safely restart Jenkins, use the following URL:

```
localhost:8080/safeRestart
```

---

## **Terminology: Slaves, Nodes, Agents**

The terms **Slaves, Nodes, and Agents** in Jenkins are interchangeable and mean the same thing.


# **Jenkins Installation on Windows Machine**

## **Step 1: Download Jenkins**

1. Browse to the official [Jenkins download page](https://www.jenkins.io/download/).
2. Under the "Downloading Jenkins" section, find the LTS (Long-Term-Support) version.
3. Click on the **Windows** text link to start downloading the Jenkins server.

---

## **Step 2: Download JDK 21**

1. Browse to the [JDK 21 download page](https://www.oracle.com/in/java/technologies/downloads/).
2. Under "Java Downloads," find Java versions like JDK 21, JDK 23.
3. Click on **JDK 21**, select Windows, and download the **x64 Installer**.

---

## **Step 3: Set Up JDK 21 Path in System Environment Variables**

1. Open **Windows System Environment Variables** in the Windows search bar.
2. Select **Environment Variables**.
3. Click on **New** under **System Variables**, enter:
   - **Variable Name**: `JAVA_HOME`
   - **Variable Value**: Path of the JDK installation directory
4. Click **OK**.
5. Select **Path** under System Variables, click **Edit**, then **New**, and add the JDK 21 path.

---

## **Step 4: Install Jenkins**

1. Double-click on the downloaded **Jenkins installer file**.
2. Follow the setup wizard:
   - Click **Next**.
   - Check the **Destination Folder** path and click **Next**.
   - In the **Service Logon Credentials**, select **Run service as a local system**, then click **Next**.
   - In the **Port Section**, click **Test Port**, then **Next**.
   - In **Jenkins Version Setup**, select the downloaded JDK path and click **Next**.
   - In **Custom Setup**, keep default settings and click **Next**.
   - Click **Install** and confirm when prompted.

---

## **Step 5: Unblock Jenkins**

1. After installation, open your browser and enter: `http://localhost:8080`.
2. Navigate to the unlock Jenkins page and locate the admin password:
   - Open the following file:
     ```
     C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword
     ```
   - Use a terminal (e.g., Git Bash) to read the file:
     ```
     cat C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword
     ```
3. Copy the password and paste it into the **Administrator password** field.
4. Click **Continue** to proceed.

---

## **Step 6: Customize Jenkins**

1. Click **Install suggested plugins** to install common plugins.
2. After installation, create the first admin user:
   
   | Field         | Value        |
   |--------------|-------------|
   | Username     | admin        |
   | Password     | admin123     |
   | Confirm Password | admin123 |
   | Full Name    | Your Name    |
   | Email Address | Your Email  |
   
3. Click **Save and Continue**.

---

## **Notes: Start or Stop Jenkins on Windows**

1. Open **Windows Search**, type **Services**, and open it.
2. Locate **Jenkins** in the list.
3. Choose an action: **Start, Stop, or Restart** the Jenkins service.

---


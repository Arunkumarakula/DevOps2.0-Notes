# GIT (Global Information Tracker)

## Why do we need a Version Control System (VCS)?

- **Collaboration**: Enables multiple people to work on the project without conflicts.
- **Storing versions**: Tracks and saves different versions of the project.
- **Figuring out what happened**: Allows you to see who made changes and why.
- **Backup**: Provides a history of changes for data recovery.

## What is VCS?
A Version Control System (VCS) is a software tool that helps developers manage changes to source code, documents, or any collection of files over time. It tracks and records every modification made to the files, allowing users to revert to previous versions, compare changes, and collaborate efficiently with others.

## Types of Version Control Systems (VCS)

### 1. Local Version Control (LVC)
- The practice of having the version database in the local computer.
- The local database keeps a record of the changes made to files in the version database.

**Drawbacks:**
- **Issue**: Multiple people working on the same project can create conflicts and challenges with coordination.
- **Solution**: This issue is addressed by Centralized Version Control (CVC).

### 2. Centralized Version Control (CVC)
- CVC resolves the issues faced in Local Version Control by maintaining a central repository where all versioned files are stored.
- Users can check out files from the central repository, make changes locally, and then check them back into the central repository.

**Drawback:**
- **Issue**: If the central server fails or becomes unavailable, the entire system can go down, as all changes depend on the server.
- **Solution**: This issue is addressed by Distributed Version Control Systems (DVCS).

### 3. Distributed Version Control (DVCS) (Remote Server)
- In DVCS, the version database is stored both on the user's local system and on a remote server.
- Users work with their local copies of files, making changes and committing them locally. Then, they can upload (push) or download (pull) changes from the remote server.
- If either the central server or a local machine fails, other copies of the repository on client systems can be used to restore the project.

## Basic Workflow of Git

### 1. Initialize or Clone a Repository
- **Initialize**: If you're starting a new project, you can initialize a new Git repository.
  ```sh
  git init
  ```
  The `git init` command is used to initialize a new Git repository in a directory. It creates a hidden `.git` directory that stores all the metadata and version history for the repository.
- **Clone**: If you're working on an existing project, clone the repository from a remote server (e.g., GitHub, GitLab).
  ```sh
  git clone https://github.com/username/repository.git
  ```
  The `git clone` command creates a copy of a remote Git repository on your local machine, including all files, branches, and commit history.

### 2. Working Directory
- The working directory (workspace) is the directory on your local machine where you edit and make changes to your project files.

### 3. Staging Area (Index)
- The staging area (index) is an intermediate area where you prepare changes before committing them to the repository.

### 4. Local Repository
- A local version of the repository where committed changes are stored on your machine.

### 5. Remote Repository
- A server-based repository where all collaborators push their changes and pull updates.

## What is Git?
- Git is a **distributed version control system (DVCS)** used to track changes in source code during software development.
- Every action is tracked, ensuring all changes are recorded and can be accessed or reverted if necessary.

## Git File Workflow

1. **Git Local Repository & Remote Repository**
   - A local repository is a user's personal copy of the versioned database.
   - The user accesses and works with all files through the local repository and then pushes any changes to the remote repository.

2. **Workspace**
   - The workspace is the user's active directory where they create and modify files.

3. **Staging Area**
   - The staging area is where all modified files, marked to be committed, are placed before being committed to the local repository.

4. **Clone**
   - The clone command creates a copy of an existing remote repository on the local machine.

5. **Commit**
   - The commit command saves all the changes in the staging area to the local repository.

6. **Push**
   - The push command uploads all the committed changes from the local repository to the remote repository.

7. **Fetch**
   - The fetch command retrieves changes made in the remote repository without merging them.

8. **Pull**
   - The pull command retrieves changes from the remote repository and merges them into the current working directory.

## Branching Strategies in GitHub

### 1. Base Branch
- The default branch, often named "main" or "master."

### 2. Develop (Development Branch)
- Used for collaborative development tasks.

### 3. QA (Quality Assurance)
- Used for testing and validating code before merging into production.

### 4. Release
- Used to prepare new releases of the application.

### 5. Feature
- Used for developing new features or functionality.

### 6. Hotfix
- Used for addressing bugs or issues in production.

### 7. Production
- The branch where the application is hosted.

## What is a Pull Request?
- A pull request is a way to propose changes to a project, request feedback, and then merge those changes into the main codebase.

### Why use pull requests?
- **Code Review**: Allows others to review your changes before they are added to the main project.
- **Collaboration**: Helps teams collaborate while maintaining a clean and stable codebase.
- **History & Discussion**: Keeps a record of discussions around a change.

## Personal Access Token (PAT)
- A secure way to authenticate yourself when interacting with GitHub’s API or performing Git operations (like cloning, pushing, or pulling) without using your GitHub password.

## Fork
- A fork is a copy of a repository under your own GitHub account, allowing you to experiment with changes without affecting the original repository.

## Tags
- A Git tag is a way to mark specific commits in your project’s history.
- Tags are used to capture specific versions of your project.

## Important Git Operations and Rules
- Git does not automatically add new files to the repository.
- Commit history is never automatically deleted.
- A branch is a separate version of the main repository.
- `git fetch origin` retrieves all the change history of the remote repository.
- `git pull` is a combination of fetch and merge.


### Ways to Clone a Git Repository

## 1. Using HTTPS

**Syntax:**
```sh
git clone https://github.com/username/repository.git
```
- Easy to use, works in most environments.
- Requires you to enter your GitHub credentials (username/password or personal access token) every time you interact with the remote repository.

---

## 2. Using SSH

**Syntax:**
```sh
git clone git@github.com:username/repository.git
```
- No need to enter credentials repeatedly after setting up SSH keys.
- Requires initial setup of SSH keys.

### How to Create SSH Keys?

1. Enter the command in the terminal (as root user):
   ```sh
   ssh-keygen
   ```
2. The keys will be generated in:
   ```
   /root/.ssh/id_rsa
   ```
3. Check the public key with the following command and copy the SSH public key:
   ```sh
   cat /root/.ssh/id_rsa.pub
   ```
4. Open GitHub:
   - Click on your profile icon.
   - Choose **Settings**.
   - Navigate to **SSH and GPG Keys**.
   - Click **Add new SSH key** and paste the public SSH key.

5. Now, you can clone using SSH.

---

## 3. Using GitHub CLI

**Syntax:**
```sh
gh repo clone username/repository
```
- Integrates well with GitHub features like issues, pull requests, etc.
- Requires installation of the GitHub CLI tool.
```
Here’s your content in Markdown format:  

```markdown
# Delete a File in GitHub Using Command Line

## **Steps to Delete a File from GitHub**

### **1. Clone Your Remote Repository Locally**
**Syntax:**
```sh
git clone <URL of Repository>
```

---

### **2. Change to the Cloned Repository**
**Syntax:**
```sh
cd <Repo-name>
```

---

### **3. Choose the File to Delete**
**Syntax:**
```sh
rm <file-name>
```

---

### **4. Add the Deleted File to the Staging Area**
**Syntax:**
```sh
git add <file-name>
```

---

### **5. Commit the Changes**
**Syntax:**
```sh
git commit -m "abc"
```

---

### **6. Push the Changes to GitHub**
**Syntax:**
```sh
git push
```





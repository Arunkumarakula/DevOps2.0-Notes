## Apache Maven

Apache Maven is a build automation and project management tool primarily used for Java projects. It simplifies the build process by managing project dependencies, compiling source code, packaging binaries, and running tests. Maven uses a Project Object Model (POM), defined in an XML file (pom.xml).

### Features of Maven

- Maven is widely used in Java and is a key tool for developers working on large-scale projects.
- Maven automatically downloads and manages libraries (dependencies) required for the project from repositories like Maven Central.
- By using the pom.xml file, Maven ensures that builds are consistent and reproducible across different environments.
- Maven supports multi-module projects, allowing you to manage and build multiple related projects together.
- Maven follows a standard project structure (e.g., `src/main/java` for source code, `src/test/java` for tests), reducing the need for explicit configuration.
- **Plugins**: Maven's functionality is extended through plugins, which can be used for tasks like compiling code, generating documentation, or deploying artifacts.

## pom.xml

The core of a Maven project is the `pom.xml` file, which contains project metadata, dependencies, and build configuration.

## Build Lifecycle

- Maven defines a build lifecycle with phases like **compile, test, package, install, and deploy**. Each phase executes a specific set of tasks.
- Maven executes a series of phases (e.g., validate, compile, test, package) to build the project.

## Repositories

- Maven downloads dependencies from remote repositories (e.g., Maven Central) and stores them in a local repository on your machine.

### Maven Repository Flow

1. When a developer executes an `mvn` command, it checks in the local repository.
2. If not found in the local repository, it searches in the remote repository.
3. If found in the remote repository, the required dependency or plugin is stored in the local repository.
4. The artifact is then used from the local repository.

## Artifacts

- The output of a Maven build is an **artifact** that can be deployed or shared.
- Maven artifacts include files such as `.war`, `.jar`, `.ear` used by a Maven project.
- Maven artifacts are stored in repositories and can be used as dependencies by other projects.
- Maven artifacts are identified by:
  1. **Group ID**: A unique identifier for the group or organization.
  2. **Artifact ID**: A unique identifier for the artifact within the group.
  3. **Version**: Also called artifact coordinates.

## Maven Advantages

- Provides a consistent project structure.
- Automates compiling, testing, and packaging.
- Easily integrates with CI tools like **Jenkins**.
- Supports environment-specific configurations (development, production, etc.).

## Common Maven Commands

```sh
mvn clean      # Cleans the project by deleting the target directory.
mvn compile    # Compiles the source code.
mvn test       # Runs unit tests.
mvn package    # Packages the compiled code into a distributable format (e.g., JAR).
mvn install    # Installs the artifact into the local repository.
mvn deploy     # Deploys the artifact to a remote repository.
```

## How Maven Works

- Reads the `pom.xml` file to understand the project configuration.
- Downloads and manages dependencies.
- Executes build lifecycle phases (e.g., compile, test, package).
- Uses plugins to perform specific tasks.
- Generates artifacts and stores them in the local or remote repository.

## .m2 Folder

The `.m2` folder is a local repository used by Apache Maven to store project dependencies, plugins, and metadata.

- It plays a crucial role in making builds **faster, consistent, and reliable**.
- **Path:**
  - Windows: `C:\Users\<username>\.m2`
  - Linux: `/home/<username>/.m2`

## Prerequisites

- **JDK (Java Development Kit)** installed.
- **Maven** installed on your system.
- Set `MAVEN_HOME` and update the `PATH` environment variable.
- Internet access for downloading dependencies.

## Directory and File Structure

- `target/` : Contains build outputs (e.g., `.war`, `.jar` files).
- `src/` : Contains source code and resources.
- `settings.xml` : Configures global or user-specific Maven settings.
- `pom.xml` : Defines project configuration, dependencies, and build settings.
- `pom.properties` : Metadata about the project, such as `groupId`, `artifactId`, and `version`.

## Maven Architecture

- **Remote Repository**: Refers to an organization-level repository.
- **Local Repository**: Refers to the developer's local machine (e.g., `.m2` folder).
- **Central Repository**: Maintained by Apache Maven.

## Maven Built-in Lifecycle

There are three built-in lifecycles in Maven:

1. **Default**: Handles project deployment.
   - Phases: `validate`, `compile`, `test`, `package`, `verify`, `install`, `deploy`
2. **Clean**: Cleans the project by removing previous build outputs.
   - Phase: `clean`
3. **Site**: Generates project documentation.
   - Phases: `site`, `site-deploy`

## Apache Maven Installation on Windows

### Step 1: Install Apache Maven

- Go to the browser and search **Install Apache Maven**.
- Choose **Downloads** and select **Binary zip archive (apache-maven-3.9.9-bin.zip)**.
- After downloading, extract the file and move it to `C:\Program Files\Maven`.

### Step 2: Install Java

- Go to [Oracle's Java Downloads](https://www.oracle.com/in/java/technologies/downloads/).
- Choose Windows and download **JDK (x64 Installer)**.
- Move the downloaded file to `C:\Program Files\Java`.
- Install Java.

### Step 3: Edit System Environment Variables

- Open **Edit System Environment Variables**.
- Select **Environment Variables** > **System Variables**.
- Click **New System Variable** and set `MAVEN_HOME` to your Maven installation path.
- Edit the **Path** variable and add paths for **Maven** and **Java**.

### Step 4: Add Maven Path in System Variables

- Add `%MAVEN_HOME%\bin` to the system path.
- Reference: [Maven Installation Guide](https://phoenixnap.com/kb/install-maven-windows).

### Step 5: Verify Installation

Open the terminal and run:

```sh
mvn -v    # Displays Maven version
java -v   # Displays Java version
```


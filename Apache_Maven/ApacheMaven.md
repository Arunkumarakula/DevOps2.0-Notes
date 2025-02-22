# Apache Maven

Apache Maven is a build automation and project management tool primarily used for Java projects. It simplifies the build process by managing project dependencies, compiling source code, packaging binaries, and running tests. Maven uses a Project Object Model (POM), defined in an XML file (`pom.xml`).

## Features of Maven

- Maven is widely used in Java and is a key tool for developers working on large-scale projects.
- It automatically downloads and manages libraries (dependencies) required for the project from repositories like Maven Central.
- By using the `pom.xml` file, Maven ensures that builds are consistent and reproducible across different environments.
- Maven supports multi-module projects, allowing you to manage and build multiple related projects together.
- Maven follows a standard project structure (e.g., `src/main/java` for source code, `src/test/java` for tests), reducing the need for explicit configuration.
- **Plugins**: Maven's functionality is extended through plugins, which can be used for tasks like compiling code, generating documentation, or deploying artifacts.

## `pom.xml`

The core of a Maven project is the `pom.xml` file, which contains project metadata, dependencies, and build configuration.

## Build Lifecycle

- Maven defines a build lifecycle with phases like `compile`, `test`, `package`, `install`, and `deploy`. Each phase executes a specific set of tasks.
- Maven executes a series of phases (e.g., validate, compile, test, package) to build the project.

## Repositories

- Maven downloads dependencies from remote repositories (e.g., Maven Central) and stores them in a local repository on your machine.

### Maven Repository Flow:

1. When a developer executes an `mvn` command, Maven first checks the local repository.
2. If the dependencies and plugins are found locally, they are used immediately.
3. If not found in the local repository, Maven searches the remote repository.
4. Once downloaded from the remote repository, dependencies or plugins are stored in the local repository for future use.

## Artifacts

- The output of a Maven build is an **artifact** (e.g., JAR, WAR, EAR files) that can be deployed or shared.
- Maven artifacts are stored in repositories, so they can be used as dependencies by other projects.
- Artifacts are identified by three components:
  1. **Group ID**: A unique identifier for the group or organization.
  2. **Artifact ID**: A unique identifier for the artifact within the group.
  3. **Version**: Also called artifact coordinates.

## Maven Advantages

- Provides a consistent project structure, making collaboration easier.
- Automates compiling, testing, and packaging steps.
- Easily integrates with CI/CD tools like Jenkins for automated builds.
- Allows configuration of different environments (e.g., development, production) seamlessly.

## Common Maven Commands

```bash
mvn clean      # Cleans the project by deleting the target directory.
mvn compile    # Compiles the source code.
mvn test       # Runs unit tests.
mvn package    # Packages the compiled code into a distributable format (e.g., JAR).
mvn install    # Installs the artifact into the local repository.
mvn deploy     # Deploys the artifact to a remote repository.
```

## How Maven Works in Real-Time

1. Reads the `pom.xml` file to understand project configuration.
2. Downloads and manages dependencies.
3. Executes build lifecycle phases (e.g., compile, test, package).
4. Uses plugins to perform specific tasks.
5. Generates artifacts and stores them in the local or remote repository.

## `.m2` Folder

The `.m2` folder is a local repository used by Apache Maven to store project dependencies, plugins, and metadata. It plays a crucial role in making builds faster, consistent, and reliable.

### `.m2` Folder Path:
- **Windows**: `C:\Users\<YourUsername>\.m2`
- **Linux**: `/home/<YourUsername>/.m2`

## Prerequisites for Using Maven

- JDK (Java Development Kit) installed.
- Maven installed on your system.
- `MAVEN_HOME` set and `PATH` environment variable updated.
- Internet access for downloading dependencies.

## Maven Directory and File Structure

- **`target/`**: Contains build outputs (e.g., WAR, JAR files).
- **`src/`**: Contains source code and resources.
- **`settings.xml`**: Configures global or user-specific Maven settings.
- **`pom.xml`**: Defines project configuration, dependencies, and build settings.
- **`pom.properties`**: Metadata about the project, such as `groupId`, `artifactId`, and `version`.

## Maven Architecture

- **Remote repository**: Organization-level repository.
- **Local repository**: User's local machine (`.m2` folder).
- **Central repository**: Apache Maven’s official repository.

## Maven Built-in Lifecycle

Maven has three built-in lifecycles:

1. **Default Lifecycle** (Handles project deployment):
   - Phases: `validate`, `compile`, `test`, `package`, `verify`, `install`, `deploy`.

2. **Clean Lifecycle** (Cleans the project by removing previous build outputs):
   - Phase: `clean`.

3. **Site Lifecycle** (Generates project documentation):
   - Phases: `site`, `site-deploy`.

# Apache Maven Installation on Windows

## Step 1: Install Apache Maven

- Open a browser and search for **Install Apache Maven**.
- Navigate to the [Maven download page](https://maven.apache.org/download.cgi).
- Choose **Binary zip archive** (e.g., `apache-maven-3.9.9-bin.zip`).
- Download and extract the file.
- Move the Maven folder to `C:\Program Files`.

## Step 2: Install Java

- Open a browser and search for **Install Java for Windows**.
- Download the latest JDK from [Oracle's official website](https://www.oracle.com/java/technologies/downloads/).
- Choose **Windows (x64 Installer)** and download the file.
- Move the downloaded file to `C:\Program Files` and install it.

## Step 3: Edit System Environment Variables

- Open **Edit System Environment Variables** in the Windows search bar.
- Select **Environment Variables** > **System Variables**.
- Click **New System Variable**, enter a name, and provide the Maven and Java paths.
- Click **Path** under **System Variables**, then **Edit**, select **New**, and add the Maven and Java paths.
- Click **OK** to save changes.

## Step 4: Add Maven Path to System Variables

- Add `%MAVEN_HOME%\bin` to the system variables.
- This allows running Maven commands globally.

## Step 5: Verify Installation

- Open a terminal and check if Maven and Java are installed:

```bash
mvn -v   # Displays the Maven version.
java -version   # Displays the Java version.
```
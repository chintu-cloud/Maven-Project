<img width="450" height="450" alt="image" src="https://github.com/user-attachments/assets/b351d2e0-b3f4-4843-98c8-7ea20a9e2c34" />       <img width="396" height="396" alt="image" src="https://github.com/user-attachments/assets/3a43c698-9ea5-44c6-991c-8bbef79ed4da" />



# 🚀  Maven Project 🚀
---
A complete, step-by-step Maven workflow guide


A sample multi-module Maven project demonstrating build lifecycle, packaging, and deployment on AWS EC2.

---

## 📖 Table of Contents
1. [Overview](#overview)
2. [Maven Goals](#maven-goals)
3. [Important Notes](#important-notes)
4. [Launch Server (AWS EC2)](#launch-server-aws-ec2)
5. [Project Structure](#project-structure)
6. [Build & Run](#build--run)
7. [Modules](#modules)

---

## 📌 Overview
This project showcases:
- Maven build lifecycle (`clean`, `compile`, `test`, `package`, `install`)
- Multi-module setup (`project-java`, `project-secret`, `sample-module`, etc.)
- Deployment on AWS EC2 with Maven and Git.

---

## ⚙️ Maven Goals

| Command        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `mvn clean`    | Cleans previous build files                                                 |
| `mvn compile`  | Compiles source code into bytecode                                          |
| `mvn test`     | Runs unit tests to validate functionality                                   |
| `mvn package`  | Creates final package (`.jar`, `.war`, `.ear`)                              |
| `mvn install`  | Installs package into local repository and project directory                |

---

## 🔑 Important Notes
1. **Before running `mvn package`:**
   ```bash
   run: (automatic)
                            mvn clean
                            mvn compile
                            mvn test
   then run:
                            mvn package
   ```

2. **Before running `mvn test`:**
   ```bash
    run: (automatic)
                            mvn clean
                            mvn compile
   then run:
                            mvn test
   ```

---

## ☁️ Launch Server (AWS EC2)

**EC2 Setup:**
- Name: `maven-java-project`
- Instance type: `t3.micro`
- Networking: Default
- Security group: Default
- Keypair: Not required

**Connect & Install:**
```bash
sudo su -
yum install maven -y        # Installs Maven + Java
mvn --version
yum install git -y
git clone https://github.com/chintu-cloud/Maven-Project.git
cd Maven-Project
tree
```

---

## 📂 Project Structure

```plaintext
           tree


.
├── README.md
├── file1
├── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── project
│   │   │           └── App.java
│   │   └── resources
│   │       └── config.properties
│   └── test
│       └── java
│           └── com
│               └── project
│                   └── AppTest.java
└── target
    ├── classes
    │   ├── META-INF
    │   │   ├── MANIFEST.MF
    │   │   └── maven
    │   │       └── com.tcs
    │   │           └── project
    │   │               ├── pom.properties
    │   │               └── pom.xml
    │   ├── com
    │   │   └── project
    │   │       └── App.class
    │   └── config.properties
    ├── maven-status
    │   └── maven-compiler-plugin
    │       ├── compile
    │       │   └── default-compile
    │       │       ├── createdFiles.lst
    │       │       └── inputFiles.lst
    │       └── testCompile
    │           └── default-testCompile
    │               ├── createdFiles.lst
    │               └── inputFiles.lst
    ├── surefire-reports
    │   ├── 2024-06-02T18-27-34_470-jvmRun1.dump
    │   ├── 2024-06-02T18-27-34_470-jvmRun1.dumpstream
    │   ├── 2024-06-02T18-27-34_470.dumpstream
    │   ├── 2024-06-02T18-33-49_067-jvmRun1.dump
    │   ├── 2024-06-02T18-33-49_067-jvmRun1.dumpstream
    │   └── 2024-06-02T18-33-49_067.dumpstream
    └── test-classes
        └── com
            └── project
                └── AppTest.class

28 directories, 22 files


```
          ls
          mvn archetype:generate  
                 OR
          mvn archetype:generate -DgroupId=com.mycompany -DartifactId=sample-module
```
```            
after run mvn archetype:generate
     enter:

      Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): 2293: 3593
then enter:
```
      [INFO] ----------------------------------------------------------------------------
      [INFO] Using following parameters for creating project from Archetype: angular-spring-archetype:0.0.6
      [INFO] ----------------------------------------------------------------------------
      [INFO] Parameter: groupId, Value: apple
      [INFO] Parameter: artifactId, Value: project-java
      [INFO] Parameter: version, Value: 1.0-SNAPSHOT
      [INFO] Parameter: package, Value: apple
      [INFO] Parameter: packageInPathFormat, Value: apple
      [INFO] Parameter: package, Value: apple
      [INFO] Parameter: groupId, Value: apple
      [INFO] Parameter: artifactId, Value: project-java
      [INFO] Parameter: version, Value: 1.0-SNAPSHOT
``` 
```
```
          ls
          cd project-java
          mvn clean 
```
```
            output: 
                       [INFO] Scanning for projects...
                       [INFO] 
                       [INFO] -------------------------< alexa:project-java >-------------------------
                       [INFO] Building project-java 1.0-SNAPSHOT
                       [INFO] --------------------------------[ war ]---------------------------------
                       [INFO] 
                       [INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ project-java ---
                       [INFO] ------------------------------------------------------------------------
                       [INFO] BUILD SUCCESS
                       [INFO] ------------------------------------------------------------------------
                       [INFO] Total time:  0.304 s
                       [INFO] Finished at: 2025-11-25T10:31:23Z
                       [INFO] ------------------------------------------------------------------------

```bash
ls 
tree
```

```plaintext
.
├── PROJECT-JAR
│   └── pom.xml
├── README.md
├── file1
├── pom.xml
├── project-1
│   └── pom.xml
├── project-java
│   └── pom.xml
├── project-secret
│   └── pom.xml
├── sample-module
│   └── pom.xml
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── project
│   │   │           └── App.java
│   │   └── resources
│   │       └── config.properties
│   └── test
│       └── java
│           └── com
│               └── project
│                   └── AppTest.java
└── target
    ├── classes
    │   ├── META-INF
    │   │   ├── MANIFEST.MF
    │   │   └── maven
    │   │       └── com.tcs
    │   │           └── project
    │   │               ├── pom.properties
    │   │               └── pom.xml
    │   ├── com
    │   │   └── project
    │   │       └── App.class
    │   └── config.properties
    ├── maven-status
    │   └── maven-compiler-plugin
    │       ├── compile
    │       │   └── default-compile
    │       │       ├── createdFiles.lst
    │       │       └── inputFiles.lst
    │       └── testCompile
    │           └── default-testCompile
    │               ├── createdFiles.lst
    │               └── inputFiles.lst
    ├── surefire-reports
    │   ├── 2024-06-02T18-27-34_470-jvmRun1.dump
    │   ├── 2024-06-02T18-27-34_470-jvmRun1.dumpstream
    │   ├── 2024-06-02T18-27-34_470.dumpstream
    │   ├── 2024-06-02T18-33-49_067-jvmRun1.dump
    │   ├── 2024-06-02T18-33-49_067-jvmRun1.dumpstream
    │   └── 2024-06-02T18-33-49_067.dumpstream
    └── test-classes
        └── com
            └── project
                └── AppTest.class

33 directories, 27 files


```

---

## 🏗️ Build & Run

**Clean project:**
```bash
mvn clean
```

**Compile project:**
```bash
mvn compile
```

**Run tests:**
```bash
mvn test
```

**Package project:**
```bash
mvn package
```

**Install locally:**
```bash
mvn install
```

---

## 📦 Modules
- **PROJECT-JAR** → JAR packaging
- **project-java** → WAR packaging
- **project-secret** → Custom module
- **sample-module** → Example submodule
- **project-1** → Additional module

---

✨ This README ensures anyone cloning your repo can **understand, build, and run** the project step by step.
```




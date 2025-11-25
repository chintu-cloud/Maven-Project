
# 🚀 Maven Project 🚀

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
   mvn clean
   mvn compile
   mvn test
   mvn package
   ```

2. **Before running `mvn test`:**
   ```bash
   mvn clean
   mvn compile
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
.
├── README.md
├── pom.xml
├── PROJECT-JAR/
│   └── pom.xml
├── project-1/
│   └── pom.xml
├── project-java/
│   └── pom.xml
├── project-secret/
│   └── pom.xml
├── sample-module/
│   └── pom.xml
├── src/
│   ├── main/java/com/project/App.java
│   ├── main/resources/config.properties
│   └── test/java/com/project/AppTest.java
└── target/
    ├── classes/
    ├── test-classes/
    ├── surefire-reports/
    └── maven-status/
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

---

Would you like me to also add **badges** (like build status, license, Java version) at the top of the README so it looks even more polished for GitHub?


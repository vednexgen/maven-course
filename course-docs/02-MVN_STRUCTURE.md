# 🚀 Maven Project Structure & Lifecycle

## 📂 Standard Directory Layout

Maven enforces a **convention-over-configuration** approach, which means it provides a standard directory structure. Developers don’t need to configure everything manually.

```
project-name/
│
├── src/
│   ├── main/
│   │   ├── java/              # Application source code
│   │   ├── resources/         # Configuration files, property files, XMLs
│   │   └── webapp/            # Web application files (for WAR projects)
│   │
│   └── test/
│       ├── java/              # Test source code (JUnit/TestNG)
│       └── resources/         # Test-related resources
│
├── target/                    # Generated files after build (compiled classes, JARs, WARs)
│
└── pom.xml                    # Project Object Model (configuration file)
```

👉 If developers follow this layout, Maven knows where to find code, resources and tests automatically.

---

## 🏷️ Creating a Maven Project

```bash
    mvn archetype:generate -DgroupId=com.example -DartifactId=demo-project \
      -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
    
    cd demo-project
```

Generated structure:

```
demo-project/
├── src/
│   ├── main/java/com/example/App.java
│   └── test/java/com/example/AppTest.java
└── pom.xml
```

---

## 🔄 Maven Build Lifecycle

Maven defines a set of **phases** that represent stages in the build process.

### Default Lifecycle Phases

1. **validate** → check project is correct.
2. **compile** → compile source code.
3. **test** → run unit tests.
4. **package** → package compiled code (JAR/WAR).
5. **verify** → run checks (integration tests, etc.).
6. **install** → install artifact into local repository (`~/.m2/repository`).
7. **deploy** → deploy artifact to remote repository.

👉 Each phase may include multiple **plugin goals**.

---

## 🧪 Hands-On: Lifecycle in Action

From inside the generated project folder:

```bash

# Validate project structure
mvn validate

# Compile source code
mvn compile

# Run tests
mvn test

# Package project into JAR
mvn package

# Install into local repository
mvn install

# (Optional) Deploy to remote repo (requires configuration)
mvn deploy
```

After running `mvn package`, check the `target/` folder:

```
target/
├── classes/              # Compiled .class files
├── test-classes/         # Compiled test classes
├── demo-project-1.0-SNAPSHOT.jar
└── surefire-reports/     # Unit test reports
```

---

## 📌 Key Notes

* Maven provides a **standardized project structure**.
* The **build lifecycle** automates tasks from compile → test → package → deploy.
* Developers only need to run `mvn <phase>` and Maven does the rest.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](01-INTRO_TO_MAVEN.md)
&emsp;&emsp;
[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](03-POM_XML.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
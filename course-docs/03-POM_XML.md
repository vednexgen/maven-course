# 🚀 Understanding `pom.xml`

## 📦 What is `pom.xml`?

* `pom.xml` stands for **Project Object Model** file.
* It is the **heart of a Maven project**, containing:

    * Project metadata
    * Dependencies
    * Plugins
    * Build configurations

👉 Without `pom.xml`, Maven cannot manage your project.

---

## 🏷️ Basic Structure of `pom.xml`

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <!-- Project Coordinates -->
    <groupId>com.example</groupId>
    <artifactId>demo-project</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>

    <name>Demo Maven Project</name>
    <description>A simple Maven project example</description>

</project>
```

### 📍 Key Elements

* **groupId** → Unique ID for project’s group/organization (like package name).
* **artifactId** → Name of the project (artifact).
* **version** → Version of the artifact.
* **packaging** → Type of packaging (`jar`, `war`, `pom`).

👉 These three (`groupId`, `artifactId`, `version`) uniquely identify a Maven artifact.

---

## 📚 Adding Dependencies

Maven manages libraries (dependencies) via **Maven Central Repository** or other repos.

Example: Adding JUnit dependency

```xml
<dependencies>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.13.2</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

👉 When you run `mvn compile/test/package`, Maven downloads this library automatically to your local repo (`~/.m2/repository`).

---

## 🔌 Adding Plugins

Plugins extend Maven’s capabilities (e.g., compiler settings, running tests, packaging jars).

**Example**: Compiler Plugin

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.10.1</version>
            <configuration>
                <source>17</source>
                <target>17</target>
            </configuration>
        </plugin>
    </plugins>
</build>
```

---

## 🌳 Super POM & Inheritance

* Every Maven project **inherits** from a default **Super POM**.
* Super POM provides default values like:

    * Source directory → `src/main/java`
    * Test directory → `src/test/java`
    * Default plugins (like compiler, surefire)

👉 Custom `pom.xml` overrides these defaults when needed.

---

## 🧪 Hands-On: Editing `pom.xml`

1. Generate a new project using quickstart archetype.
2. Open `pom.xml` → explore project coordinates.
3. Add a **JUnit dependency**.
4. Add **Maven Compiler Plugin** and set Java version to 17/25.
5. Run:

```bash
mvn clean test
```

6. Observe Maven downloading dependencies into `~/.m2/repository`.

---

## 📌 Key Notes

* `pom.xml` is the **blueprint** of a Maven project.
* Dependencies and plugins are declared inside it.
* Super POM provides defaults → you override when needed.
* Maven resolves dependencies automatically from repositories.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](02-MVN_STRUCTURE.md)
&emsp;&emsp;
[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](04-DEPENDENCY_SCOPE.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
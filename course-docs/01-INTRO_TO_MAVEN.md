# 🚀 Introduction to Build Tools & Maven Basics

## 📚 Why Do We Need Build Tools?

* In small projects, compiling with `javac` and running with `java` works.
* But as projects grow:

    * Multiple `.java` files → hard to compile manually.
    * External libraries (JARs) → hard to manage versions.
    * Testing, packaging, deployment → become manual & error-prone.

👉 Build tools solve these issues by automating compile, test, package, and deploy.

---

## 🛠 Evolution of Java Build Tools

* **Ant** → procedural build (you write “how” to build).
* **Maven** → declarative build (you say “what”, Maven knows “how”).
* **Gradle** → flexible & faster, modern alternative.

---

# 📦 What is Maven?

* Maven is a **build automation and project management tool**.
* Standardizes:

    * Project structure
    * Dependency management
    * Build lifecycle

---

## ⚙️ Installing Maven

1. Download Maven from: [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)
2. Extract the archive.
3. Set environment variables:

    * `MAVEN_HOME` or `M2_HOME`
    * Add `MAVEN_HOME/bin` to `PATH`
4. Verify installation:

   ```bash
   mvn -v
   ```

    Example output:

   ```
   Apache Maven 3.9.9
   Java version: 17.0.12
   OS: Windows 10 10.0 amd64
   ```

---

## 🧪 Hands-On: Without vs With Maven

### Case 1: Manual Compilation

```java
// Step 1: Create HelloWorld.java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}

// Step 2: Compile manually
javac HelloWorld.java

// Step 3: Run manually
java HelloWorld
```

👉 Works, but imagine adding **10 external libraries** and **100 files** → becomes painful.

---

### Case 2: Using Maven

```bash
# Generate Maven project
mvn archetype:generate -DgroupId=com.example -DartifactId=hello-maven \
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

# Move inside project
cd hello-maven

# Compile project
mvn compile

# Run tests
mvn test

# Package project into JAR
mvn package
```

👉 Notice: Maven created **standard structure**, handled compilation, and generated a JAR file.

---

## 📌 Key Notes

* Maven solves **dependency management & build automation**.
* Standard project structure → reduces confusion.
* Lifecycle ensures a repeatable, reliable build process.

---

## 📝 **Exercise**

* Install Maven on their machine.
* Run `mvn -v` and verify setup.
* Create the first Maven project and explore the generated folder structure.

---

<div style="display: flex; justify-content: space-between;">

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](../README.md)

[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](02-MVN_STRUCTURE.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---

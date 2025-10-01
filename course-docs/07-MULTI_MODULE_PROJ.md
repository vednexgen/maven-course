# 🚀 Multi-Module Maven Projects

## 📦 What is a Multi-Module Project?

* A **Multi-Module Project** allows you to build multiple related Maven projects together.
* Modules share a common parent POM.
* Useful for:

    * Large projects
    * Microservices
    * Shared libraries

---

## 🏗️ Structure of a Multi-Module Project

```
parent-project/
│
├── pom.xml                 # Parent POM
├── module1/
│   └── pom.xml             # Module 1
├── module2/
│   └── pom.xml             # Module 2
```

---

## ⚙️ Creating a Multi-Module Project

### Step 1: Create Parent Project

```bash
    mvn archetype:generate -DgroupId=com.example -DartifactId=parent-project \
      -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

### Step 2: Modify Parent `pom.xml`

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>parent-project</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>pom</packaging>

    <modules>
        <module>module1</module>
        <module>module2</module>
    </modules>

</project>
```

### Step 3: Create Modules

```bash
mvn archetype:generate -DgroupId=com.example.module1 -DartifactId=module1 \
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

mvn archetype:generate -DgroupId=com.example.module2 -DartifactId=module2 \
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

### Step 4: Modify Module `pom.xml`

```xml
<parent>
    <groupId>com.example</groupId>
    <artifactId>parent-project</artifactId>
    <version>1.0-SNAPSHOT</version>
</parent>
```

---

## 🔄 Building Multi-Module Project

From parent directory:

```bash
mvn clean install
```

👉 Maven builds all modules in defined order.

---

## 📌 Key Notes

* Multi-module projects allow **modularization**.
* Parent POM manages **common configurations**.
* Modules inherit from parent POM.
* Improves reusability and maintainability.

---

<div style="display: flex; justify-content: space-between;">

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](06-MVN_LIFECYCLE.md)

[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](08-MVN_ADVANCE.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
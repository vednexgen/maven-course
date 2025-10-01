# 🚀 Dependencies & Scopes

## 📦 What Are Dependencies?

* Dependencies are **external libraries (JARs)** required by your project.
* Instead of manually downloading JARs, Maven fetches them automatically from **Maven Central Repository** or other repositories.

👉 Defined inside `<dependencies>` in `pom.xml`.

Example:

```xml
<dependencies>
    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.10.1</version>
    </dependency>
</dependencies>
```

---

## 🔄 Transitive Dependencies

* Maven automatically includes dependencies of your dependencies.
* Example: If Library A needs Library B, Maven fetches B too.
* Helps reduce manual management but can cause **version conflicts**.

👉 Use `mvn dependency:tree` to check dependency hierarchy.

---

## 🎯 Dependency Scopes

Dependency **scope** defines **when** and **where** a dependency is available.

### 🏷️ Common Scopes

1. **compile** (default)

    * Available at compile, test, and runtime.
    * Example: Gson library.

2. **provided**

    * Available at compile but **not packaged** (container provides it).
    * Example: Servlet API (Tomcat/Jetty provides).

3. **runtime**

    * Not needed for compile, but required at runtime.
    * Example: JDBC driver.

4. **test**

    * Available only for testing.
    * Example: JUnit, Mockito.

5. **system** (rare)

    * Similar to `provided` but you explicitly provide the JAR path.

---

## 🧪 Hands-On: Exploring Scopes

`pom.xml` snippet:

```xml
<dependencies>
    <!-- Compile Scope -->
    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
        <version>2.10.1</version>
        <scope>compile</scope>
    </dependency>

    <!-- Provided Scope -->
    <dependency>
        <groupId>javax.servlet</groupId>
        <artifactId>javax.servlet-api</artifactId>
        <version>4.0.1</version>
        <scope>provided</scope>
    </dependency>

    <!-- Runtime Scope -->
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.33</version>
        <scope>runtime</scope>
    </dependency>

    <!-- Test Scope -->
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.13.2</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

Run:

```bash
mvn dependency:tree
```

👉 Observe how Maven resolves direct + transitive dependencies.

---

## ⚠️ Dependency Conflicts

* Problem: Two libraries require different versions of the same dependency.
* Solution:

    * Use `<dependencyManagement>` to control versions.
    * Exclude unwanted transitive dependencies.

Example (exclude transitive):

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
    <version>3.1.2</version>
    <exclusions>
        <exclusion>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
        </exclusion>
    </exclusions>
</dependency>
```

---

## 📌 Key Notes

* Dependencies define required external libraries.
* Maven automatically resolves **transitive dependencies**.
* Dependency **scopes** control availability (compile, test, runtime, provided).
* Use `dependency:tree` to debug conflicts.
* Manage versions using `<dependencyManagement>`.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](03-POM_XML.md)
&emsp;&emsp;
[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](05-BUILD_PLUGINS_N_GOALS.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
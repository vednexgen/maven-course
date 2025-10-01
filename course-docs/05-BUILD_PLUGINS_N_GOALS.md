# 🚀 Build Plugins & Goals

## 🔧 What Are Plugins in Maven?

* **Plugins** are used to extend Maven's functionality.
* Each plugin has **goals**, which perform specific tasks.
* Example: Compiling code, packaging JARs, running tests, generating reports, deploying artifacts.

👉 Plugins are defined in the `<build>` section of `pom.xml`.

---

## ⚙️ Goals

* A **goal** is a single task performed by a plugin.
* Example:

    * `compiler:compile` → Compiles main source code.
    * `surefire:test` → Runs unit tests.
    * `jar:jar` → Creates JAR file.

👉 You can run goals directly:

```bash
mvn compiler:compile
mvn surefire:test
```

---

## 🔄 Plugin Lifecycle Binding

* Maven automatically binds common goals to **phases**.
* Example:

    * `compile` phase → `compiler:compile`
    * `test` phase → `surefire:test`
    * `package` phase → `jar:jar`

👉 This means you don’t always need to call goals explicitly.

---

## 📦 Commonly Used Plugins

### 1. **Maven Compiler Plugin**

Compiles Java code.

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.11.0</version>
    <configuration>
        <source>1.8</source>
        <target>1.8</target>
    </configuration>
</plugin>
```

### 2. **Maven Surefire Plugin**

Runs unit tests.

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>3.1.2</version>
</plugin>
```

### 3. **Maven Jar Plugin**

Creates JAR package.

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-jar-plugin</artifactId>
    <version>3.3.0</version>
</plugin>
```

### 4. **Maven Shade Plugin**

Creates a "fat JAR" (all dependencies bundled).

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-shade-plugin</artifactId>
    <version>3.5.0</version>
    <executions>
        <execution>
            <phase>package</phase>
            <goals>
                <goal>shade</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

### 5. **Maven Clean Plugin**

Deletes `target/` directory.

```bash
mvn clean
```

---

## 🧪 Hands-On: Plugins & Goals

1. Add `maven-compiler-plugin` and set Java 8 as source/target.
2. Run:

   ```bash
   mvn clean compile
   ```

   👉 Observe how plugin compiles code.
3. Add `maven-shade-plugin` and build a fat JAR:

   ```bash
   mvn package
   ```

   👉 Check `target/` folder.

---

## 📌 Key Notes

* Plugins extend Maven’s functionality.
* Goals are tasks inside plugins.
* Many goals are bound automatically to lifecycle phases.
* Popular plugins: compiler, surefire, jar, shade.
* Plugins can be configured inside `pom.xml` under `<build>`.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](04-DEPENDENCY_SCOPE.md)
&emsp;&emsp;
[![](https://img.shields.io/badge/Next-➡️-caddd6?style=for-the-badge&labelColor=caddd6)](06-MVN_LIFECYCLE.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
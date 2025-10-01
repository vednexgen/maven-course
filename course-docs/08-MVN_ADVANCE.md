# 🚀 Advanced Maven & Best Practices

## 📚 Advanced Maven Features

Maven offers several advanced features to enhance project build, management, and maintainability.

---

### 1. Profiles

* Profiles allow different build configurations for different environments.
* Defined inside `pom.xml`.

**Example:**

```xml
<profiles>
    <profile>
        <id>dev</id>
        <properties>
            <env>development</env>
        </properties>
    </profile>
    <profile>
        <id>prod</id>
        <properties>
            <env>production</env>
        </properties>
    </profile>
</profiles>
```

Run with:

```bash
  mvn clean install -Pdev
```

---

### 2. Dependency Management

* Avoid version conflicts by centralizing dependency versions.

**Example:**

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
            <version>3.1.2</version>
        </dependency>
    </dependencies>
</dependencyManagement>
```

---

### 3. Parent POM Inheritance

* Centralize common configurations.
* Useful in multi-module projects.

**Example:**

```xml
<parent>
    <groupId>com.example</groupId>
    <artifactId>parent-project</artifactId>
    <version>1.0-SNAPSHOT</version>
</parent>
```

---

### 4. Plugin Management

* Centralize plugin configurations to avoid repetition.

**Example:**

```xml
<pluginManagement>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.11.0</version>
            <configuration>
                <source>17</source>
                <target>17</target>
            </configuration>
        </plugin>
    </plugins>
</pluginManagement>
```

---

### 5. Repository Management

* Configure remote repositories.

**Example:**

```xml
<repositories>
    <repository>
        <id>central</id>
        <url>https://repo.maven.apache.org/maven2</url>
    </repository>
</repositories>
```

---

## 📝 Best Practices for Maven Projects

1. **Follow Standard Project Structure**

    * Helps tools and IDEs recognize your project.

2. **Use Dependency Management**

    * Centralize version control.

3. **Avoid Hardcoding Versions**

    * Use properties or dependencyManagement.

4. **Use Profiles for Environment Configurations**

    * Separate dev, test, and production builds.

5. **Keep Plugins Updated**

    * Avoid compatibility issues.

6. **Use `.gitignore` for target/**

    * Avoid committing build artifacts.

7. **Document Your POM**

    * Comments help new developers understand configurations.

---

## 🧪 Hands-On: Advanced Maven

1. Create a profile for dev and prod in your `pom.xml`.
2. Use dependencyManagement to manage dependency versions.
3. Create a parent POM and inherit it in a child project.
4. Use pluginManagement to centralize compiler plugin configuration.

---

## ✨ Summary

* Profiles → environment-specific builds.
* Dependency Management → centralized version control.
* Parent POM → common configuration for multi-module projects.
* Plugin Management → centralized plugin configuration.
* Repository Management → control repository sources.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](07-MULTI_MODULE_PROJ.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
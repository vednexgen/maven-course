# 🚀 Maven settings.xml Explained

## 🛠 What is settings.xml?

`settings.xml` is a **configuration file** for Maven that stores **user-specific settings** — unlike `pom.xml`, which is project-specific.

Think of `pom.xml` as **"project settings"** and `settings.xml` as **"Maven installation or user settings"**.

---

## 📍 Location of settings.xml

1. **Global settings** (applies to all users):

```
{Maven_Home}/conf/settings.xml
```

Example: `C:\Program Files\apache-maven-3.x.x\conf\settings.xml`

2. **User-specific settings** (applies only to your user):

```
${user.home}/.m2/settings.xml
```

Example (Windows): `C:\Users\<username>\.m2\settings.xml`

---

## 🔹 Uses of settings.xml

### **1. Repository Configuration**

Specify which repositories Maven should use.

```xml
<settings>
    <mirrors>
        <mirror>
            <id>central-mirror</id>
            <mirrorOf>central</mirrorOf>
            <url>https://my.custom.repo/repository/maven-public/</url>
        </mirror>
    </mirrors>
</settings>
```

### **2. Proxy Settings**

For working behind a corporate proxy.

```xml
<settings>
    <proxies>
        <proxy>
            <id>example-proxy</id>
            <active>true</active>
            <protocol>http</protocol>
            <host>proxy.mycompany.com</host>
            <port>8080</port>
            <username>proxyuser</username>
            <password>somepassword</password>
        </proxy>
    </proxies>
</settings>
```

### **3. Authentication for Private Repositories**

Store credentials for private repos.

```xml
<settings>
    <servers>
        <server>
            <id>private-repo</id>
            <username>myuser</username>
            <password>mypassword</password>
        </server>
    </servers>
</settings>
```

### **4. Profiles**

Environment-specific builds.

```xml
<settings>
    <profiles>
        <profile>
            <id>dev</id>
            <properties>
                <env>development</env>
            </properties>
        </profile>
    </profiles>

    <activeProfiles>
        <activeProfile>dev</activeProfile>
    </activeProfiles>
</settings>
```

### **5. Local Repository Location**

Change the default dependency storage location.

```xml
<localRepository>D:/maven-repo</localRepository>
```

---

### 📌 Key Notes 

#### Difference Between pom.xml and settings.xml

| File         | Purpose                                  |
| ------------ | ---------------------------------------- |
| pom.xml      | Project-specific configuration           |
| settings.xml | User or Maven installation configuration |

---

💡 **Example:**
If your company has a private repository or proxy, you'll **configure it once in `settings.xml`**, not in every `pom.xml`.

---

<div>

[![](https://img.shields.io/badge/Prev-⬅️-caddd6?style=for-the-badge&labelColor=caddd6)](08-MVN_ADVANCE.md)

</div>

[![](https://img.shields.io/badge/Back_To_Intro-🔙-d6cadd?style=for-the-badge&labelColor=d6cadd)](../README.md)

---
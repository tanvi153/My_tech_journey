# DevOps Lecture Notes

## 1. What is DevOps?

DevOps (**Development + Operations**) is a culture and set of practices
that combines software development and IT operations to deliver software
faster and more reliably.

### Goals

-   Reduce manual work through automation
-   Faster software delivery
-   Continuous Integration (CI)
-   Continuous Deployment (CD)
-   Better collaboration
-   Improved software quality

> **Jenkins** is commonly used to automate building, testing, and
> deployment.

------------------------------------------------------------------------

## 2. SDLC (Software Development Life Cycle)

### Definition

SDLC is the structured process used to develop software from idea to
maintenance.

### Phases

1.  Requirement Gathering
2.  Planning
3.  Design
4.  Development
5.  Testing
6.  Deployment
7.  Maintenance

### Problems with Traditional SDLC

-   Manual deployment
-   Slow releases
-   More human errors
-   Communication gap between Development and Operations

------------------------------------------------------------------------

## 3. SDLC vs DevOps

  SDLC                DevOps
  ------------------- ----------------------
  Sequential          Continuous
  Manual deployment   Automated deployment
  Slow releases       Frequent releases
  Separate teams      Collaborative teams
  More manual work    More automation

------------------------------------------------------------------------

## 4. Agile Basics

Agile develops software in **small iterations (Sprints)** instead of one
large release.

### Sprint

A Sprint is a fixed development cycle (typically 1--4 weeks).

### Advantages

-   Faster delivery
-   Customer feedback
-   Easy requirement changes
-   Better quality

------------------------------------------------------------------------

## 5. DevOps Lifecycle

``` text
Plan
 ↓
Code
 ↓
Build
 ↓
Test
 ↓
Release
 ↓
Deploy
 ↓
Operate
 ↓
Monitor
 ↓
Repeat
```

### Common Tools

  Stage     Tools
  --------- ---------------------
  Plan      Jira
  Code      Git
  Build     Maven, Gradle
  Test      JUnit, Selenium
  Deploy    Jenkins
  Monitor   Prometheus, Grafana

------------------------------------------------------------------------

## 6. DevOps Roles

-   **Developer** -- Writes code.
-   **Tester (QA)** -- Tests the application.
-   **DevOps Engineer** -- Automates CI/CD, deployment, and
    infrastructure.
-   **Operations Engineer** -- Manages servers and production.
-   **Security Engineer (DevSecOps)** -- Handles application security.

------------------------------------------------------------------------

## 7. Popular DevOps Tools

  Tool            Purpose
  --------------- --------------------------
  Git             Version Control
  GitHub/GitLab   Code Repository
  Maven           Build Tool
  Jenkins         CI/CD
  Docker          Containerization
  Kubernetes      Container Orchestration
  Ansible         Configuration Management
  Terraform       Infrastructure as Code
  Prometheus      Monitoring

------------------------------------------------------------------------

## 8. JAR, WAR, and EAR Files

### JAR (Java Archive)

-   Extension: `.jar`
-   Contains compiled Java classes and libraries.
-   Used for standalone Java applications and reusable libraries.

### WAR (Web Application Archive)

-   Extension: `.war`
-   Used for Java web applications.
-   Contains Servlets, JSPs, HTML, CSS, JavaScript, `WEB-INF`, and
    libraries.
-   Deployed on servers such as Apache Tomcat.

### EAR (Enterprise Archive)

-   Extension: `.ear`
-   Packages multiple JAR and WAR modules into one enterprise
    application.
-   Used on enterprise application servers.

### Comparison

  -----------------------------------------------------------------------
  Feature                    JAR            WAR            EAR
  -------------------------- -------------- -------------- --------------
  Purpose                    Java           Web            Enterprise
                             App/Library    Application    Application

  Extension                  .jar           .war           .ear
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 9. Environment Variables, HOME Folder, PATH, CLASSPATH, and System Properties

### Environment Variables

Environment variables store important system configuration values used
by applications.

Examples: - `JAVA_HOME` - `PATH` - `CLASSPATH`

### HOME Folder

The HOME directory is the default personal directory of a user.

**Linux**

``` bash
/home/username
```

**Windows**

``` text
C:\Users\Username
```

Check HOME in Linux:

``` bash
echo $HOME
```

### PATH

The PATH variable tells the operating system where to search for
executable programs.

Example:

If Java is installed in:

``` text
C:\Program Files\Java\jdk-21\bin
```

Adding this folder to PATH allows:

``` bash
java
javac
```

to run from any directory.

### JAVA_HOME

Points to the root JDK installation folder (not the `bin` directory).

Example:

``` text
C:\Program Files\Java\jdk-21
```

### CLASSPATH

CLASSPATH tells the Java compiler and JVM where to find additional
classes and external libraries required by your application.

Without the required library in the classpath, Java may throw:

``` text
ClassNotFoundException
```

**Difference**

  PATH                        CLASSPATH
  --------------------------- ----------------------------------
  Finds executable programs   Finds Java classes and libraries
  Used by the OS              Used by Java

### System Properties -\> Boot -\> I/O

System properties are configuration values provided to the Java Virtual
Machine (JVM) that describe the runtime environment.

#### Boot

The **Boot** process starts the JVM and loads essential Java runtime
classes before your application runs. The Bootstrap Class Loader loads
core Java libraries (such as `java.lang`), allowing the JVM to
initialize.

#### I/O (Input/Output)

I/O refers to how a Java program reads input and writes output.

Examples: - Reading keyboard input - Reading files - Writing files -
Printing output to the console - Network communication

Java provides the `java.io` and `java.nio` packages for I/O operations.

**Simple Flow**

``` text
Computer Starts
      ↓
Operating System
      ↓
JVM Starts (Boot)
      ↓
Core Java Classes Loaded
      ↓
Your Program Executes
      ↓
Program Performs I/O (Read/Write Data)
```

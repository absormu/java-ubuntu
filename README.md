# java-ubuntu
How To Install Java 15 On Ubuntu 20.04 LTS

# Download JDK
https://www.oracle.com/java/technologies/javase-jdk15-downloads.html

# Install JDK
```java
# Make directory for Oracle JDK
sudo mkdir -p /usr/java/oracle

# CD
cd /usr/java/oracle

# Copy the download to Oracle JDKs directory
sudo cp /home/absor/Downloads/jdk-15.0.1_linux-x64_bin.tar.gz jdk-15.0.1_linux-x64_bin.tar.gz

# Extract JDK
sudo tar -xzvf jdk-15.0.1_linux-x64_bin.tar.gz
```

# Set Environment Variables
```java
# Update Profile
sudo nano /etc/profile

# Java 15
JAVA_HOME=/usr/java/oracle/jdk-15.0.1
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export PATH

```

# Configure Java Commands
```java
# Check version
java -version

# Output
Command 'java' not found, but can be installed with:

sudo apt install openjdk-11-jre-headless  # version 11.0.8+10-0ubuntu1~20.04, or
sudo apt install default-jre              # version 2:1.11-72
sudo apt install openjdk-13-jre-headless  # version 13.0.3+3-1ubuntu2
sudo apt install openjdk-14-jre-headless  # version 14.0.1+7-1ubuntu1
sudo apt install openjdk-8-jre-headless   # version 8u265-b01-0ubuntu2~20.04

# Configure Java Alternatives
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/java/oracle/jdk-15.0.1/bin/java" 1

# Configure Javac Alternatives
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/java/oracle/jdk-15.0.1/bin/javac" 1

# Check version
java -version

# Output
java version "15.0.1" 2020-10-20
Java(TM) SE Runtime Environment (build 15.0.1+9-18)
Java HotSpot(TM) 64-Bit Server VM (build 15.0.1+9-18, mixed mode, sharing)

# Use only in case of multiple JDKs installed

# Configure Java
sudo update-alternatives --config java

# Configure Java Compiler
sudo update-alternatives --config javac

```
# Hello World
```java
>sudo mkdir -p /data/programs/java
>cd /data/programs/java
>sudo nano HelloWorld.java

// Hello World
public class HelloWorld {

        // The main method
        public static void main( String[] args ) {

                // Print Hello World
                System.out.println( "Hello World !!" );
        }
}

// Compile the program
sudo javac HelloWorld.java

// Execute the program
sudo java HelloWorld

// Program output
Hello Java !!

```
link https://java.tutorials24x7.com/blog/how-to-install-java-15-on-ubuntu-20-04-lts

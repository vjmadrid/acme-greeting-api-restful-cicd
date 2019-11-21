# Configuration Maven Plugins

List of plugins to facilitate the operations to carry out with Maven

Step to follow:

* Check Prerequisites
* List of Plugins





## Check Prerequisites

* Verify that the Maven is installed
* Verify that your project have integration with Maven





## List of Plugins

Note : Add to the plugins area <plugins> or in a specific way to the established profile.

BUILD
- [spring-boot-maven-plugin](#spring-boot-maven-plugin)
- [maven-resources-plugin](#maven-resources-plugin)
- [maven-compiler-plugin](#maven-compiler-plugin)
- [maven-verifier-plugin](#maven-verifier-plugin)

TESTING
- [maven-surefire-plugin](#maven-surefire-plugin)




### <a name="spring-boot-maven-plugin">spring-boot-maven-plugin</a>

Plugin used to work with Spring Boot application

https://docs.spring.io/spring-boot/docs/current/maven-plugin/usage.html

```bash
<plugins>
	...
	<plugin>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-maven-plugin</artifactId>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version

List of Goals
* Goal "run" : Execute Spring Boot application
* Goal "repackage" : Create Jar / War auto-executable
* Goal "build-info" : Generate a build information that can be used by the Actuator
* ...

```bash
mvn spring-boot:run
```





### <a name="maven-resources-plugin">maven-resources-plugin</a>

Plugin used to handle the project resources

https://maven.apache.org/plugins/maven-resources-plugin/

```bash
<properties>
	...
	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    ...
</properties>

<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-resources-plugin</artifactId>
		<version>X.Y.Z</version>
		<configuration>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version or Normal Version

Note : Core Plugins

* Configure resource Encoding : UTF-8
* Copy files from a input resource directory to a output directory
* Replace placeholder variables in the resource file
* ...

List of Goals	
* Goal "resources" : copy resources for main source code
* Goal "testResources" : copy resources for test source code
* Goal "copy-resources" : copy resources for arbitrary source code

```bash
mvn resources:resources
```





### <a name="maven-compiler-plugin">maven-compiler-plugin</a>

Plugin used to compile the project source

https://maven.apache.org/plugins/maven-compiler-plugin/

```bash
<properties>
	...
	<java.version>1.8</java.version>
	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    ...
</properties>

<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-compiler-plugin</artifactId>
		<version>X.Y.Z</version>
		<configuration>
			<source>${java.version}</source>
			<target>${java.version}</target>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```


Use Spring Boot Version or Normal Version

Note : Core Plugins

* Configure compilation version : source and target
* Configure encoding
* ...

List of Goals
* Goal "compile" : Compile main source files
* Goal "testCompile" : Compile test source files

```bash
mvn compiler:compile
```





### <a name="maven-verifier-plugin">maven-verifier-plugin</a>m

Plugin used to verify the existence of files and directories

https://maven.apache.org/plugins/maven-verifier-plugin/

```bash
<properties>
	...
	<verifier.verification.file>src/test/verifier/verifications-test.xml</verifier.verification.file>
    ...
</properties>

<plugins>
	...
	<plugin>
        <artifactId>maven-verifier-plugin</artifactId>
        <version>X.Y.Z</version>
        <configuration>
            <verificationFile>${verifier.verification.file}</verificationFile>
            <failOnError>false</failOnError>
        </configuration>
        <executions>
			<execution>
				<id>main</id>
				<phase>verify</phase>
				<goals>
					<goal>verify</goal>
				</goals>
			</execution>
		</executions>
    </plugin>
	...
</plugins>
```

Use Spring Boot Version or Normal Version

Configuration with a verification File

List of Goals
* Goal "verify" : Verify the existence od files and directories

```bash
mvn verifier:verify
```





### maven-surefire-plugin [Spring Boot Version] 

Plugin used to run unit tests 


## Authors

* **Víctor Madrid**

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
		<configuration>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version

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
		<configuration>
			<source>${java.version}</source>
			<target>${java.version}</target>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```


Use Spring Boot Version

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

1. Configure Verifier File

```bash
<verifications
  xmlns="http://maven.apache.org/verifications/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/verifications/1.0.0
  http://maven.apache.org/xsd/verifications-1.0.0.xsd">
    <files>
        <file>
            <location>README.md</location>
            <contains>acme-greeting-api-restful</contains>
        </file>
        <file>
            <location>src/main/resources/application.yml</location>
        </file>
        <file>
            <location>src/main/resources/application-uat.yml</location>
        </file>
        <file>
            <location>src/main/resources/application-prod.yml</location>
        </file>
        <file>
            <location>src/main/resources/custom-banner.txt</location>
        </file>
        <file>
            <location>src/main/resources/logback.xml</location>
        </file>
        <file>
            <location>src/test/resources/logback-test.xml</location>
        </file>
    </files>
</verifications>
```

2. Configure Plugin

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
		<version>1.1</version>
        <configuration>
            <verificationFile>${verifier.verification.file}</verificationFile>
            <failOnError>true</failOnError>
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

Use Version : 1.1

List of Goals
* Goal "verify" : Verify the existence od files and directories

```bash
mvn verifier:verify
```





### <a name="maven-surefire-plugin">maven-surefire-plugin</a>

Plugin used to run unit tests

https://maven.apache.org/surefire/maven-surefire-plugin/

```bash
<properties>
	...
	<skip.all.tests>false</skip.all.tests>
	<skip.unit.tests>false</skip.unit.tests>
	<skip.integration.tests>false</skip.integration.tests>
    ...
</properties>

<profiles>
	...
	<profile>
		<id>dev</id>
		<properties>
			...
			<skip.unit.tests>false</skip.unit.tests>
			..
		</properties>
	</profile>
	...
</profiles>

<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-surefire-plugin</artifactId> <!-- surefire plugin version managed by Spring Boot -->
		<configuration>
			<skipTests>${skip.unit.tests}</skipTests>
		</configuration>
		<executions>
			<execution>
				<id>unit-tests</id>
				<phase>test</phase>
				<goals>
					<goal>test</goal>
				</goals>
				<configuration>
					<skipTests>${skip.unit.tests}</skipTests>
					<includes>
						<include>**/*Test.java</include>
					</includes>
				</configuration>
			</execution>
			<execution>
				<id>integration-tests</id>
				<phase>integration-test</phase>
				<goals>
					<goal>test</goal>
				</goals>
				<configuration>
					<skipTests>${skip.integration.tests}</skipTests>
					<includes>
						<include>**/*IT.*</include>
					</includes>
				</configuration>
			</execution>
		</executions>
	</plugin>
	...
</plugins>
```

Your properties can be configured

A good approach can be to configure it by environment

Use Spring Boot Version or Normal Version

Note : Core Plugins

* Execute test
* Generate report/surefire-reports
* Integration with normal test executions
* ...

List of Goals
* Goal "help" : Display help information
* Goal "test" : Run tests using Surefire

```bash
mvn surefire:test

or 

mvn test
```




### <a name="jacoco-maven-plugin">jacoco-maven-plugin</a>

Plugin used to generate code coverage

https://www.eclemma.org/jacoco/trunk/doc/maven.html

```bash
<properties>
	...
	<start-class>com.acme.xxx.yyy.zzzl.Application</start-class>
    ...
</properties>

<plugins>
	...
	<plugin>
				<groupId>org.jacoco</groupId>
				<artifactId>jacoco-maven-plugin</artifactId>
				<version>0.8.5</version>
				<executions>

					<execution>
						<id>coverage-initialize</id>
						<goals>
							<goal>prepare-agent</goal>
						</goals>
					</execution>
					<execution>
						<id>coverage-report</id>
						<phase>test</phase>
						<goals>
							<goal>report</goal>
						</goals>
						<configuration>
							<outputDirectory>target/jacoco-report</outputDirectory>
						</configuration>
					</execution>
					
				</executions>
			</plugin>
	...
</plugins>
```

Use Version : 0.8.5

* Create report : target/site/jacoco/index.html
* Create Check with diferent configuration
* ...

List of Goals
* Goal "help" 
* Goal "prepare-agent"
* Goal "prepare-agent-integration"
* Goal "merge"
* Goal "report"
* Goal "report-integration"
* Goal "report-aggregate"
* Goal "check"
* Goal "dump"
* Goal "instrument"
* Goal "restore-instrumented-classes"

```bash
mvn test
```


## Authors

* **Víctor Madrid**

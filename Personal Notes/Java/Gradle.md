# build.gradle
```java
import com.github.spotbugs.snom.SpotBugsTask  
  
plugins {  
    id 'java'  
    id 'application'  
    id 'com.google.protobuf' version '0.9.4'  
    id "com.github.spotbugs" version "5.0.13"  
    id "checkstyle"  
}  
  
// Allow the command gradle run to run main  
application {  
    mainClass = 'Main'  
}  
  
repositories {  
    mavenCentral()  
}  
  
dependencies {  
    // Implement JUnit for tests  
    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.9.0'  
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine:5.9.0'  
    testImplementation 'org.junit.jupiter:junit-jupiter-params:5.9.0'  
    // Includes a bundle of above  
    testImplementation 'org.junit.jupiter:junit-jupiter:5.9.0'  
  
    // Implement json objects  
    implementation 'org.json:json:20240303'  
  
    // Able to read, and write json  
    implementation 'com.fasterxml.jackson.core:jackson-databind:2.17.0'  
  
    // Implements protobuf  
    implementation 'com.google.protobuf:protobuf-java:3.25.3'  
  
    // Password decryption  
    implementation 'org.mindrot:jbcrypt:0.4'  
}  
  
test {  
    useJUnitPlatform()  
}  
  
protobuf {  
    protoc {  
        artifact = 'com.google.protobuf:protoc:3.25.3'  
    }  
    generatedFilesBaseDir = "$projectDir/password-manager/src/generated"  
}  
  
run {  
    standardInput = System.in  
}  
  
tasks.register('runServer', JavaExec) {  
    group = "application"  
    description = "Run the socket server"  
    classpath = sourceSets.main.runtimeClasspath  
    mainClass.set('SimpleServer')  
}  
  
tasks.register('runClient', JavaExec) {  
    group = "application"  
    description = "Run the socket client"  
    classpath = sourceSets.main.runtimeClasspath  
    mainClass.set('SimpleClient')  
}  
  
checkstyle {  
    toolVersion = "8.8"  
    configDirectory = file("config/checkstyle") // able to use "${conig_loc}"  
    configFile = file("config/checkstyle/checkstyle.xml")  
    // Keep checkstyle a little quieter  
    ignoreFailures = true  
    showViolations = false  
}  
  
tasks.withType(Checkstyle) {  
    reports {  
        html.required.set(true)  
        xml.required.set(false)  
    }  
}  
checkstyle {  
    toolVersion = "8.8"  
}  
  
// To generate an HTML report instead of XML  
spotbugs {  
    toolVersion = '4.8.4'  
    ignoreFailures = true  
    showProgress = true  
    effort = 'max'  
    reportLevel = 'low'  
}  
  
tasks.withType(SpotBugsTask).configureEach {  
    reports {  
        html.required.set(true)  
        xml.required.set(false)  
    }  
}
```
# Gradle Wrapper
- Make the gradlew executable for the github action "Java and Gradle"
	- git update-index --chmod=+x gradlew
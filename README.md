1. Gradle is a build automation tool is used to automate the creation of applications.
2. Gradle is popular to provide high-speed performance, nearly twice as fast as Maven.
3. A build script is known as build.gradle and is located in the root directory of the project. 
4. Gradlew is a gradle wrapper for gradle command.
5. gradlew is a wrapper(w - character) that uses gradle.
6. gradle-wrapper.properties contain the gradle wrapper configuration information

### Testing Gradle

`./gradlew test`

### Building (no tests)

`./gradlew assemble`

### Building (with tests)

`./gradlew build`

### Running in Docker

`./gradlew assemble docker dockerRun`

### Stopping Docker container

`./gradlew dockerStop`

### Deploying to AWS

`./gradlew awsCfnMigrateStack awsCfnWaitStackComplete -PsubnetId=<your-subnet-id> -Pregion=<your-region>`

### Deleting AWS deployment

`./gradlew awsCfnDeleteStack awsCfnWaitStackComplete`

## Using API

* get all rides - GET [/ride](http://localhost:8080/ride) to get a list of all the rides
* get specific ride - GET [/ride/${id}](http://localhost:8080/ride/1) to get a specific ride
* create ride - POST JSON to [/ride](http://localhost:8080/ride) to create a new ride 
(see [article](https://tomgregory.com/building-a-spring-boot-application-in-jenkins/#2_Trying_out_our_Spring_Boot_application) for full details)


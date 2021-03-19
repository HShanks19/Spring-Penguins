pipeline{
        agent any
        stages{
            stage('Build/Test'){
                steps{
                    sh "mkdir jenkins-tutorial-test"
                }
            }
            stage('Deploy'){
                steps{
                    java -jar target/spring-penguins-0.0.1-SNAPSHOT.jar
                }
            }
        }
}

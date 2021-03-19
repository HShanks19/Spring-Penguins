pipeline{
        agent any
        stages{
            stage('Build/Test'){
                steps{
                    sh 'mvn --version'
                    
                }
            }
            stage('Deploy'){
                steps{
                    java -jar target/spring-penguins-0.0.1-SNAPSHOT.jar
                }
            }
        }
}

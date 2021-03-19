pipeline{
        agent any
        stages{
            stage('Build/Test'){
                steps{
                    git url: 'https://github.com/HShanks19/Spring-Penguins'

                      // Run the maven build
                      sh "mvn clean verify"
                    
                }
            }
            //stage('Deploy'){
                //steps{
                   // java -jar target/spring-penguins-0.0.1-SNAPSHOT.jar
               // }
            //}
        }
}

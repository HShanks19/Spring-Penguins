pipeline{
        agent any
        stages{
            stage('Build/Test'){
                steps{
                    git url: 'https://github.com/HShanks19/Spring-Penguins'

                    withMaven(
                        maven: 'maven3.6.3', // (1)
                        // Use `$WORKSPACE/.repository` for local repository folder to avoid shared repositories
                        mavenLocalRepo: '.repository', // (2)
                        // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
                        // We recommend to define Maven settings.xml globally at the folder level using
                        // navigating to the folder configuration in the section "Pipeline Maven Configuration / Override global Maven configuration"
                        // or globally to the entire master navigating to  "Manage Jenkins / Global Tools Configuration"
                        mavenSettingsConfig: 'my-maven-settings' // (3)
                    ) {

                      // Run the maven build
                      sh "mvn clean verify"
                    
                }
            }
            stage('Deploy'){
                steps{
                    java -jar target/spring-penguins-0.0.1-SNAPSHOT.jar
                }
            }
        }
}

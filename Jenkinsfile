pipeline{
        agent any
        stages{
            stage('Build'){
                steps{
                      sh "mvn clean package"
                }
            }
            stage('Test') {
                    steps {
                        sh 'mvn test'
                    }
                    post {
                        always {
                            junit 'target/surefire-reports/*.xml'
                            step([$class: 'CoberturaPublisher', autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: '**/coverage.xml', failUnhealthy: false, failUnstable: false, maxNumberOfBuilds: 0, onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false])
                        }
                    }
                }
            stage('Deploy') { 
                    steps {
                       sh 'java -jar target/spring-penguins-0.0.1-SNAPSHOT.jar'
                    }
                }
        }
}

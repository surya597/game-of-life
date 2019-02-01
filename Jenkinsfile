pipeline 
{
    agent any
    stages{
        stage ('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }      
        } 
            stage ('Deploy to Production'){
              steps{
                build job: 'Deploy-to-Prod'
            } 
        }
     }
   }
 


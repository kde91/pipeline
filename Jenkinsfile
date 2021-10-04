pipeline{
    agent any
    stages{
        stage ('build'){
            steps{
            echo 'I am build Stage...............'
            }
        }
        stage ('test'){
            steps{
            echo 'I am in test Stage...............'
            }
        }
        stage ('staging'){
            steps{
            echo 'I am Staging...............'
            }
        }
      
      stage ('parallel'){
        parallel{
          stage('Unit Test'){
            steps{
              echo "Running unit test"
            }
          } 
          
      stage('Int Test'){
            steps{
              echo "Running Int test"
            }
          } 
        }
      }   
         stage ('release'){
             steps{
            echo 'I am Staging...............'
             }
        }
    }
   
}
post {
    failure {
        mail to: 'kdwebs91@gmail.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
}

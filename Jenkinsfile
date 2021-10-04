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
         stage ('release'){
             steps{
            echo 'I am Staging...............'
             }
        }
    }
   
post {
    
    success {
        mail to: 'kdwebs91@gmail.com',
             subject: "Successful Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
    
    failure {
        mail to: 'kdwebs91@gmail.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
  }
}
    

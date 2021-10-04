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
        mail to: 'karnajit.de@capgemini.com',
             subject: "Successful Pipeline: ${currentBuild.fullDisplayName}",
             body: "You can check your logs for this successful build in : ${env.BUILD_URL}"
    }
    
    failure {
        mail to: 'karnajit.de@capgemini.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
  }
}
    

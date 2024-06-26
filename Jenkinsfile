pipeline {
  agent any 
  stages {
    stage ("code checkout") {
      steps {
        git 'https://github.com/1234shaik/game-of-life.git'
      }
    }
        stage('Build') {
            steps {
                script {
                    bat 'mvn clean test -e -X'
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'target/surefire-reports/*.xml', allowEmptyArchive: true
            junit 'target/surefire-reports/*.xml'
        }
        failure {
            mail to: 'shaikakramit5@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something went wrong with the pipeline."
        }
    }
}


      
  

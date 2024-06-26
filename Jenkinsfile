pipeline {
  agent any 
  stages {
    stage ("code checkout") {
      steps {
        git 'https://github.com/1234shaik/game-of-life.git'
      }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'mvn clean test -e -X'
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
            mail to: 'you@example.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something went wrong with the pipeline."
        }
    }
}
}

      
  

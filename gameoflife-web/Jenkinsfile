pipeline {
  agent any 
  stages {
    stage ("code checkout") {
      steps {
        git 'https://github.com/1234shaik/game-of-life.git'
      }
    }
    stage ("build") {
      steps {
        sh 'mvn install'
      }
    }
  }
}
      
  

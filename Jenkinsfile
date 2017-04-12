pipeline {
  agent {
    docker {
      image 'ubuntu:latest'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Hello from docker'
            
          },
          "Test": {
            echo 'Testing'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying'
      }
    }
  }
}
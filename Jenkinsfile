pipeline {
  agent {
    docker {
      image 'ubuntu:latest'
      args '-u root:root'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Hello from docker'
            echo '${sh(returnStdout: true, script: \'env\')}'
            
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
  environment {
    HOME = '$WORKSPACE'
  }
}
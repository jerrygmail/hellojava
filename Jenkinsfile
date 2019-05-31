pipeline {
  agent any
  stages {
    stage('trying blue ocean') {
      steps {
        echo 'hello world'
        sleep 5
        isUnix()
        pwd()
      }
    }
    stage('stage2') {
      steps {
        echo 'This stage 2'
      }
    }
    stage('deploy') {
      steps {
        echo 'Copying to artifactory'
        bat(script: 'c:\\artifactory\\copyartifact.bat', returnStatus: true, returnStdout: true)
      }
    }
     post { 
        success { 
            echo 'Success!'
        }
        failure { 
            echo 'Build failed!'
        }
    }
  }
}

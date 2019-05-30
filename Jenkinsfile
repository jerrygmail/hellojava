pipeline {
  agent any
  stages {
    stage('trying blue ocean') {
      steps {
        echo 'hello world'
        input('Do you want to proceed?')
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
  }
}

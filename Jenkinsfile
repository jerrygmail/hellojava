pipeline {
  agent any
  stages {
    stage('trying blue ocean') {
      steps {
        echo 'hello world'
        sleep 5
        isUnix()
        pwd()
        emailext(subject: 'test', body: 'test', from: 'jerry.manaloto@sprint.com', replyTo: 'jerry.manaloto@sprint.com', to: 'jerry.manaloto@sprint.com')
      }
    }
  }
}
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
        curl -uadmin:password -T C:\Jerry\java\hello.class "http://localhost:8081/artifactory/example-repo-local/"
      }
    }
  }
}

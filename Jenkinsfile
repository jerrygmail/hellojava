pipeline {
  agent any
  stages {
    stage('trying blue ocean') {
      steps {
        echo 'hello world'
        sleep 5
        isUnix()
        pwd()
        echo "$BUILD_NUMBER"
echo "$BUILD_ID"
echo "$BUILD_DISPLAY_NAME"
echo "$JOB_NAME"
echo "$JOB_BASE_NAME"
echo "$BUILD_TAG"
echo "$EXECUTOR_NUMBER"
echo "$NODE_NAME"
echo "$NODE_LABELS"
echo "$WORKSPACE"
echo "$JENKINS_HOME"
echo "$JENKINS_URL"
echo "$BUILD_URL"
echo "$JOB_URL"
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

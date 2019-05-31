pipeline {
  agent any
  stages {
    stage('trying blue ocean') {
      steps {
        echo 'hello world'
        sleep 5
        isUnix()
        pwd()
        echo "Buildnumber:$BUILD_NUMBER"
echo "Build id:$BUILD_ID"
echo "$Build display name:BUILD_DISPLAY_NAME"
echo "Job Name:$JOB_NAME"
echo "Job Base Name:$JOB_BASE_NAME"
echo "Build Tag:$BUILD_TAG"
echo "Executor Number:$EXECUTOR_NUMBER"
echo "Node name:$NODE_NAME"
echo "Node Labels:$NODE_LABELS"
echo "Workspace:$WORKSPACE"
echo "Jenkins Home:$JENKINS_HOME"
echo "Jenkins URL:$JENKINS_URL"
echo "Build URL:$BUILD_URL"
echo "Job URL:$JOB_URL"
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

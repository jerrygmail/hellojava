pipeline {

  agent any

  triggers {
        pollSCM '* * * * *'
    }
  parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
          }
  stages {
    stage('build') {
          when {
	branch 'prod'
	}
      steps {
        echo "Hello ${params.PERSON}"
        echo 'hello world'
        sleep 5
        isUnix()
        pwd()
        echo "Buildnumber:$BUILD_NUMBER"
        echo "Build id:$BUILD_ID"
echo "Build display name:$BUILD_DISPLAY_NAME"
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
    when {
	branch 'prod'
	}
      steps {
        echo 'This stage 2'
      }
    }
    stage('deploy') {
	    when {
	branch 'prod'
	}
      steps {
        echo 'Copying to artifactory'
        bat(script: 'c:\\artifactory\\copyartifact.bat', returnStatus: true, returnStdout: true)
      }
    }
  }
     post { 
	 
        success { 
            echo 'Success!'
            mail to:"jerry.manaloto@sprint.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
        }
        failure { 
            echo 'Build failed!'
          mail to:"jerry.manaloto@sprint.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
        }
    }
  }

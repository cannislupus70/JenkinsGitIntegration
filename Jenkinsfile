pipeline {
  agent any
  
  environment {
    DIRECTORY_PATH = "/Users/cannis_lupus/Desktop/SIT753 PROFESSIONAL PRACTICE"
    TESTING_ENVIRONMENT = "test sight"
    PRODUCTION_ENVIRONMENT = "NEVIL SUKHADIYA"
  }
  
  stages {
    stage('Build') {
      steps {
        echo "Fetch the source code from the directory path $DIRECTORY_PATH"
        echo "Compile the code and generate any necessary artifacts"
      }
      post{
        success {
            mail to: "nevilsukhadiya1234@gmail.com"
            subject: "Build Status Email"
            body: "Build was successful!"
        }
      }
    }
    stage('Test') {
      steps {
        echo "Running unit tests"
        echo "Running integration tests"
      }
    }
    stage('Code Quality Check') {
      steps {
        echo "Checking the quality of the code"
      }
    }
    stage('Deploy') {
      steps {
        echo "Deploying the application to $TESTING_ENVIRONMENT"
      }
    }
    stage('Approval') {
      steps {
        sleep time: 10, unit: 'SECONDS'
      }
    }
    stage('Deploy to Production') {
      steps {
        echo "Deploying the application to $PRODUCTION_ENVIRONMENT"
      }
    }
  }
}
pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      environment {
        LOG_LEVEL = 'INFO'
      }
      steps {
        echo "Building Release ${RELEASE} with log level ${LOG_LEVEL}..."
      }
    }

    stage('Test'){
      steps {
        echo "Testing Release ${RELEASE}"
      }
    }
      stage('Deploy'){
        input{
          message 'Deploy'
          ok 'Do it !'
          parameters {
            string(name: TARGET_ENVIRONMENT',defaultValue: 'PROD',description: 'Target deployment environment')
          }
        }
      steps {
        echo "Deploying Release ${RELEASE} to environment ${TARGET_ENVIRONMENT}"
      }
    }
  }
  post{
      always {
        echo "Prints whether deploy was success or failure..."
      }
    }               
  environment {
    RELEASE = '20.05'
  }
}

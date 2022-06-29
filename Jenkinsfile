pipeline {
  agent any
  environment {
    somePath = "${env.SOME_ENV_PATH}"
    awsRegion = "${env.AWS_REGION}"
  }
  stages {
    stage('Print my stuff') {
      steps {
        echo "somePath environment var is [${somePath}]"
        echo "awsRegion environment var is [${awsRegion}]"
      }
    }
    stage("Check JAVA version") {
      steps {
        sh "java --version"
      }
    }

  }
  post {
    always {
      cleanWs()
    }
  }
}

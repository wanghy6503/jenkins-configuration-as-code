pipeline {
    agent any
    environment {
        // Global Jenkins environment properties
        somePath = "${env.SOME_ENV_PATH}"
        awsRegion = "${env.AWS_REGION}"
    }
    tools {
        // we set up these tools in the Configuration as Service yaml
        jdk "jdk11"
        maven "maven3"
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
      stage("Check MAVEN version") {
            steps {
                sh "mvn --version"
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}

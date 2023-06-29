pipeline {
  agent any
  stages {
    stage('stage Build') {
      steps {
        sh 'sh \'mvn -B -DskipTests clean package\''
      }
    }

    stage('stage Test') {
      steps {
        sh 'sh \'mvn test\''
        junit 'junit \'target/surefire-reports/*.xml\''
      }
    }

    stage('stage Delivery') {
      steps {
        sh 'sh \'./jenkins/scripts/deliver.sh\''
      }
    }

  }
}
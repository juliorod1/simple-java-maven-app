pipeline {
  agent any
  stages {
    stage('stage Build') {
      steps {
        sh 'mvn -B -DskipTests clean package '
      }
    }

    stage('stage Test') {
      steps {
        sh 'mvn test'
        junit 'junit \'target/surefire-reports/*.xml\''
      }
    }

    stage('stage Delivery') {
      steps {
        sh 'sh ./simple-java-maven-app/jenkins/scripts/deliver.sh'
      }
    }

  }
}
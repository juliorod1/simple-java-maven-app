pipeline {
  agent any
  stages {
    stage('stage Build') {
      steps {
        sh 'sh /root/apache-maven-3.9.3/bin/mvn -B -DskipTests clean package'
      }
    }

    stage('stage Test') {
      steps {
        sh 'sh /root/apache-maven-3.9.3/bin/mvn test'
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
pipeline {
  agent any
  stages {
    stage('stage Build') {
      steps {
        sh '''export  PATH=/root/apache-maven-3.9.3/bin:$PATH
mvn -B -DskipTests clean package'''
      }
    }

    stage('stage Test') {
      steps {
        sh '''export  PATH=/root/apache-maven-3.9.3/bin:$PATH
mvn test'''
        junit 'junit \'target/surefire-reports/*.xml\''
      }
    }

    stage('stage Delivery') {
      steps {
        sh '''sh export  PATH=/root/apache-maven-3.9.3/bin:$PATH
sh ./simple-java-maven-app/jenkins/scripts/deliver.sh'''
      }
    }

  }
  environment {
    MVN = '/root/apache-maven-3.9.3/bin'
  }
}
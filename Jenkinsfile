pipeline {
  agent { label 'linux' }
  tools {
    maven 'Maven 3.54'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/effectivejenkins/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'echo "JAVA_HOME..."'
        sh 'echo $JAVA_HOME'
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}

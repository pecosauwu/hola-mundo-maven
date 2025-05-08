pipeline {
  agent any

  triggers {
    cron('*/5 * * * *')
  }

  stages {
    stage('Build con Maven') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Run App') {
      steps {
        sh 'java -cp target/classes com.ejemplo.App'
      }
    }
  }
}

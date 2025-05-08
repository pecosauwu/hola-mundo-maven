pipeline {
  agent any

  // Se agrega el cron que compila cada 5 minutos
  triggers {
    cron('*/5 * * * *')
  }
  stages {
    stage('Checkout') {
      steps {
        // Se clona el repositorio
        git credentialsId: 'github-hola-mundo',
            url: 'https://github.com/pecosauwu/hola-mundo-maven.git'
      }
    }
    stage('Build con Maven') {
      steps {
        // Limpia, compila y empaqueta en modo batch
        sh 'mvn -B clean package'
      }
    }
    stage('Run App') {
      steps {
        // Ejecuta la clase principal
        sh 'java -cp target/classes com.ejemplo.App'
      }
    }
  }
}

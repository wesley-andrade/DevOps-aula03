pipeline {
  agent any
  stages {
    stage('Clonar repositório') {
      steps {
        git 'https://github.com/wesley-andrade/DevOps-aula03.git'
      }
    }
    stage('Build da aplicação') {
      steps {
        script {
          sh 'docker-compose down'
          sh 'docker-compose build'
          sh 'docker-compose up -d'
        }
      }
    }
  }
  post {
    success {
      echo 'Build concluído com sucesso!'
    }
    failure {
      echo 'O build falhou.'
    }
  }
}

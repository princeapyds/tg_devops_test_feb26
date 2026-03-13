pipeline {
 agent any

 stages {

  stage('Clone Code') {
    steps {
        git branch: 'main', url: 'https://github.com/princeapyds/tg_devops_test_feb26.git'
    }
}

  stage('Build Docker Image') {
   steps {
    sh 'docker build -t devops-demo .'
   }
  }

  stage('Stop Old Container') {
   steps {
    sh 'docker stop demo || true'
    sh 'docker rm demo || true'
   }
  }

  stage('Run New Container') {
   steps {
    sh 'docker run -d -p 80:5000 --name demo devops-demo'
   }
  }

 }
}

pipeline {
  agent any
  stages {
    stage('Cleanup') {
      steps {
        sh 'Jenkins/clean.sh'
      }
    }

    stage('build') {
      steps {
        sh 'sudo docker build /home/ubuntu/workspace/Test/ -t test'
      }
    }

    stage('deploy') {
      steps {
        sh 'sudo docker run -ti -p 82:80 -d test '
      }
    }

  }
}
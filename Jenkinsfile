pipeline {
  agent any
  stages {
    stage('Cleanup') {
      steps {
        sh 'sudo docker rm -f $(sudo docker ps -a -q)'
      }
    }

    stage('build') {
      steps {
        sh 'sudo docker build /home/ubuntu/workspace/devopsIQ_master/ -t test'
      }
    }

    stage('deploy') {
      steps {
        sh 'sudo docker run -ti -p 82:80 -d test '
      }
    }

  }
}
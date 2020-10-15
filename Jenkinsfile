pipeline {
  agent any
  stages {
    stage('build image') {
      steps {
        sh 'docker login -u ${USERNAME} -p ${PASSWORD} 192.168.50.246:9083'
        sh '''docker.withRegistry(\'http://192.168.50.246:9083\') {
    	docker.build(registry).push(\'latest\')
     }}'''
        }
      }

    }
    environment {
      username = 'credentials(\'DOCKER_USERNAME\')'
      password = 'credentials(\'DOCKER_PASSWORD\')'
      registry = 'azzywessy/samplescan'
    }
  }
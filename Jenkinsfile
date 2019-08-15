pipeline {
  agent any
  stages {
    stage('build-demo') {
      steps {
        bat(script: 'git checkout master && git pull origin master && npm install && npm test && npm build', label: 'build demo', returnStatus: true)
      }
    }
  }
}
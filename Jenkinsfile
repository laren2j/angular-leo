pipeline {
  agent any
  stages {
    stage('build-demo') {
      steps {
        bat(script: 'git reset --hard git checkout master git pull origin master npm install && npm run test & ng test --code-coverage & npm run build', label: 'build demo', returnStatus: true)
      }
    }
  }
}
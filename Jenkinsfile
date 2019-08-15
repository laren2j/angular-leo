pipeline {
  agent any
  stages {
    stage('build-demo') {
      steps {
        bat(script: 'git reset --hard git checkout master git pull origin master npm install && npm run test & ng test --code-coverage & npm run build', label: 'build demo', returnStatus: true)
        warnError(message: 'build-demo-status', catchInterruptions: true) {
          emailext(subject: 'build-demo-status', body: 'build-demo-status', attachLog: true, compressLog: true, from: 'ldsouza@datainnovations.com', presendScript: 'ldsouza@datainnovations.com', replyTo: 'ldsouza@datainnovations.com', to: 'ldsouza@datainnovations.com')
        }

      }
    }
  }
}
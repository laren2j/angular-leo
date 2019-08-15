pipeline {
  agent any
  stages {
    stage('build-demo') {
      steps {
        bat(script: 'git checkout master && git pull origin master && npm install && npm test && npm build', label: 'build demo', returnStatus: true)
        catchError(buildResult: 'Failed', catchInterruptions: true, message: 'build-demo failed', stageResult: 'Failed') {
          emailext(subject: 'Build failed', body: 'Build failed', attachLog: true, compressLog: true, from: 'laren2j@gmail.com', replyTo: 'laren2j@gmail.com', to: 'laren2j@gmail.com')
        }

      }
    }
  }
}
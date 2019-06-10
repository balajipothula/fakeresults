pipeline {
  agent any
  stages {
    stage('fakeresult') {
      steps {
        git(url: 'https://github.com/balajipothula/fakeresults.git', branch: 'master')
      }
    }
  }
}
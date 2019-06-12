pipeline {
  agent {
    docker {
      image 'balajipothula/tomcat:8.5.40'
      args '-v /root/.tomcat:/root/.tomcat'
    }
  }
  stages {
    stage('pullcode') {
      steps {
        git(url: 'https://github.com/balajipothula/fakeresults.git', branch: 'master')
      }
    }
    stage('buildwar') {
      steps {
        sh 'mvn install'
      }
    }
    stage('pushwar') {
      steps {
        sh 'curl -v -u tomcat:tomcat -T /root/.jenkins/ROOT.war "http://13.233.109.154:8080/manager/text/deploy?path=/&update=true"'
      }
    }
  }
}

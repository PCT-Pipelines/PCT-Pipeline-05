pipeline {
  agent {
    node {
      label 'maven'
    }
    
  }
  stages {
    stage('License - checks') {
      steps {
        git(url: 'http://git.app.eng.bos.redhat.com/git/jboss-prod-core/gates.git/', branch: 'master')
        load 'gates/licenses/RunGate.groovy'
      }
    }
    stage('Source code - checks') {
      steps {
        load 'gates/sourcecodelocation/RunGate.groovy'
      }
    }
    stage('CVEs - check') {
      steps {
        load 'gates/cves/RunGate.groovy'
      }
    }
  }
}
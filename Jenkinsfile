pipeline {
  agent {
      docker { image 'ubuntu:18.04' }
  }
  stages {
    stage('build') {
      steps {
          sh 'echo Building ${BRANCH_NAME}...'
	  sh 'cat /etc/os-release'
	  sh 'ls -l'
      }
    }
  }
}

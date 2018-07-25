pipeline {
  agent {
      docker { image 'alpine' }
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

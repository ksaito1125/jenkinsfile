pipeline {
  agent {
      docker { image 'maven:3.5.4-jdk-8' }
  }
  stages {
    stage('build') {
      steps {
          sh 'echo Building ${BRANCH_NAME}...'
	  sh 'cat /etc/os-release'
	  sh 'ls -l'
	  sh 'mvn --version'
	  sh 'java -version'
      }
    }
  }
}

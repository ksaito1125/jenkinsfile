pipeline {
  agent {
      docker { image 'maven:3.5.4-jdk-8' }
  }
  stages {
      stage('info') {
	  steps {
              sh 'echo Building ${BRANCH_NAME}...'
	      sh 'cat /etc/os-release'
	      sh 'ls -l'
	      sh 'mvn --version'
	      sh 'java -version'
	  }
      }
      stage('build') {
	  steps {
	      dir('my-app') {
		  sh 'mvn package'
	      }
	  }
      }
      stage('outputs') {
	  steps {
	      archiveArtifacts 'my-app/target/my-app-*.jar'
	  }
      }
  }
}

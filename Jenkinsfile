pipeline {
  agent none
  stages {
      stage('info') {
	  agent {
	      dockerfile {
		  args '-v maven:/root/.m2/repository'
	      }
	  }
	  steps {
              sh 'echo Building ${BRANCH_NAME}...'
	      sh 'cat /etc/os-release'
	      sh 'ls -l'
	      sh 'mvn --version'
	      sh 'java -version'
	      sh 'pwd'
	  }
      }
      stage('build') {
	  agent {
	      dockerfile {
		  args '-v maven:/root/.m2/repository'
	      }
	  }
	  steps {
	      dir('my-app') {
	      	  sh 'ls -l'
		  sh 'mvn package'
		  archiveArtifacts 'target/my-app-*.jar'
	      }
	  }
      }
      stage('outputs') {
	  agent {
	      docker { image 'alpine' }
	  }
	  steps {
	      sh 'cat /etc/os-release'
	  }
      }
  }
}

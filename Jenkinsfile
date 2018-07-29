pipeline {
  agent none
  stages {
      stage('info') {
	  agent {
	      dockerfile true
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
	      dockerfile true
	  }
	  steps {
	      dir('my-app') {
	      	  sh 'ls -l'
		  sh 'mvn package'
	      }
	      #archiveArtifacts 'my-app/target/my-app-*.jar'
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
  post {
      always {
          archive "target/**/*"
          junit 'my-app/target/surefire-reports/*.xml'
      }
  }
}

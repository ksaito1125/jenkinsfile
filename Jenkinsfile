pipeline {
  agent { dockerfile true }
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
  post {
      always {
          archive "target/**/*"
          junit 'my-app/target/surefire-reports/*.xml'
      }
  }
}

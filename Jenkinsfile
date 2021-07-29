pipeline {
  agent any
  environment {
    Course = 'DevOps Calgary'
    Branch = 'main'
  }
  stages {
    stage('Audit Tools') {
      steps {
        echo "Audit all tools to be used on this pipeline ${Branch}"
	sh "git --version"
	sh "node --version"
	sh "npm --version"
	sh "ng --version"
	sh "ansible --version"
	echo "Workspace Folder: ${WORKSPACE}"
      }
    }
    stage ('Install packages') {
	steps {
	  dir("${WORKSPACE}/conduit-ui") {
	    echo "Install conduit UI packages"
	    sh "npm install"
	  }
        }
      }
      stage ('Build UI') {
	steps {
	  dir("${WORKSPACE}/conduit-ui") {
	    echo "Install conduit UI packages"
	    sh "npm run build"
	  }
        }
      }
    }
  }
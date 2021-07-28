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
    stage ('Run linting') {
	steps {
	  dir("${WORKSPACE}/conduit-ui") {
	    echo "Install conduit UI packages"
	    sh "npm run lint"
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
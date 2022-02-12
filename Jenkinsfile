pipeline {
    agent any
    stages {
        stage{'Build'}{
            steps {
		sh 'echo "Building..."'
		sh 'chmod +x scripts/dockcross-build.sh'
		sh 'scripts/dockcross-build.sh'
		archiveArtifacts artifacts: 'bin/*', fingerprint: true
	    }
	}
	stage('Test'){
	    steps {
	        sh 'echo "dummy Running..."'
	   }    
	}
    }
}

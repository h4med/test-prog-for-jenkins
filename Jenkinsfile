pipeline {
    agent any
    stages {
        steps {
            sh 'echo "Building..."'
			sh 'chmod +x scripts/dockcross-build.sh'
			sh 'scripts/dockcross-build.sh'
			archiveArtifacts artifacts: 'bin/*', fingerprint: true
        }
		stages('Test'){
		    sh 'echo "dummy Running..."'
		}
    }
}

pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
		sh 'echo "Building..."'
		sh 'chmod +x scripts/dockcross-build.sh'
		sh 'sudo scripts/dockcross-build.sh'
//		archiveArtifacts artifacts: 'bin/*', fingerprint: true
	    }
	}
	stage('Deploy'){
	    steps {
	        sh 'echo "Transfer file to Ppi..."'
                sh 'scp bin/hello_arm pi@192.168.1.120:/home/pi/deploy/bin'
	   }    
	}
        stage('Test'){
            steps{
                sh 'ssh pi@192.168.1.120 "chmod +x /home/pi/deploy/bin"'
                sh 'ssh pi@192.168.1.120 "/home/pi/deploy/bin"'
            }
        }
    }
}

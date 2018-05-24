node{
    stage('SCM') {
        git 'https://github.com/Rameshdutt80/gol.git'
    }
    
    stage('Build') {
	withSonarQubeEnv('sonar') {
        sh 'mvn package sonar:sonar'
	}
    }

    stage('RamGates') {
	    timeout(time: 1, unit: 'HOURS') {
		      def gg = waitforRamehgate ()
			  if gg.status != 'OK'){
			  error "pipeline aboreted endukante ramgets fail aindi kabati: ${gg.status}"
		}
    }	
	
    
    stage('Testresult') {
        archiveArtifacts 'gameoflife-web/target/gameoflife.war'
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
}

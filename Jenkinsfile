node{
    stage('SCM') {
        git 'https://github.com/Rameshdutt80/gol.git'
    }
    
    stage('Build') {
        sh 'mvn package'
    }
    
    stage('Testresult') {
        archiveArtifacts 'gameoflife-web/target/gameoflife.war'
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
}

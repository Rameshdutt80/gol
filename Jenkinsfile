node{
    stage('vcs') {
        git 'https://github.com/Rameshdutt80/game-of-life.git'
    }
    
    stage('Build') {
        sh 'mvn package'
    }
    
    stage('Testresult') {
        archiveArtifacts 'gameoflife-web/target/gameoflife.war'
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
}

node{
    stage('SCM') {
        git 'https://github.com/Rameshdutt80/gol.git'
    }
    
  stage('SonarQube analysis') {
    withSonarQubeEnv('sonar-6') {
      sh 'mvn clean package sonar:sonar'
    } // SonarQube taskId is automatically attached to the pipeline context
  }
    
    stage('Testresult') {
        archiveArtifacts 'gameoflife-web/target/gameoflife.war'
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
}

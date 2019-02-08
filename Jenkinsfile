node {
   stage('SCM') {
       // git clone
       git 'https://github.com/ksphub/webapp.git'
   }
   stage ('build the packages') {
       // mvn package
       sh label: '', script: 'mvn package'
   }
   stage ('show test results') {
       //Testing
       junit 'target/surefire-reports/*.xml'
   }
   stage ('archival') {
       // archiving artifacts
       archiveArtifacts 'target/*.war'   
   }
}

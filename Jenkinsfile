node('labmaven1') {
   stage('SCM') {
       // git clone
       git 'https://github.com/ksphub/webapp.git'
   }
   stage ('build the packages') {
       // mvn package
       sh label: '', script: 'mvn package'
   }   
   stage ('archival') {
       // archiving artifacts2
       archiveArtifacts 'target/*.war'   
   }
}

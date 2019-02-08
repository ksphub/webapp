node {
   stage('SCM') {
       // git clone
       git 'https://github.com/ksphub/webapp.git'
   }
   node('labmaven1') {
       // mvn package
       sh label: '', script: 'mvn package'
   }     
   stage ('archival') {
       // archiving artifacts2
       archiveArtifacts 'target/*.war'   
   }
}

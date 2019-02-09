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
   stage ('nexusArtifactUploader') {
       // uploading Artifact to Nexus
	nexusArtifactUploader artifacts: [[artifactId: 'WebApp-$BUILD_TIMESTAMP', classifier: '', file: 'target/WebApp.war', type: 'war']], credentialsId: '61d480f1-d9f3-4920-96a0-4bdebac3f070', groupId: 'Prod', nexusUrl: '172.31.93.102:8081/nexus', nexusVersion: 'nexus2', protocol: 'http', repository: 'kspnrepo1', version: '$BUILD_ID'
   }
   stage ('deploy2apache') {
       // Deployment Apache
       sh label: '', script: 'sudo cp target/WebApp.war /opt/tomcat/webapps/'
   }
}

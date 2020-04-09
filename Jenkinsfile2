pipeline {
   agent any

	environment{
		ANYPOINT=credentials('ANYPOINT')
	}
   stages {
      stage('Build') {
         steps {	
         		withMaven(maven:'maven'){
         			sh 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
         		}	
              }			
      }
       stage('Deploy') {
         steps {	
         		withMaven(maven:'maven') {
         			sh 'mvn -f mule-jenkins-pipeline/pom.xml package -Dusername=AnilBawneAPRIL1 -Dpassword=Rajaram94@ -Denvironment=Development -DmiuleDeploy'
         		}	
              }	
      }
   }
}
pipeline {

  agent any
  environment {
    //adding a comment for the commit test
    DEPLOY_CREDS = credentials('deploy-anypoint-user')
    MULE_VERSION = '4.2.2'
    WORKER = "Micro"
  }
  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          bat "mvn test"
      }
    }

     stage('Deploy Development') {
      environment {
        ENVIRONMENT = 'Sandbox'
        APP_NAME = 'jenkinpoc'
      }
      steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -DmuleDeploy  -Danypoint.username=AnilBawneAPRIL1 -Danypoint.password=Rajaram94@ -Dcloudhub.app=jenkinpoc -Dcloudhub.environment=Sndbox  -Dcloudhub.worker=1'
      }
    }
  }

  tools {
    maven 'M3'
  }
}
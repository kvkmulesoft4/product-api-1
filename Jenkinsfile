pipeline {

  agent any
  environment {
  	ANYPOINT_CREDS = credentials('ANYPOINT_CREDENTIALS')
  }

  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "***** Munit test cases execution ***********"
      }
    }

     stage('Deployment') {
     
      steps {
            bat 'mvn -U -V -e -B -DskipTests -Pdev deploy -DmuleDeploy -Dusername="%ANYPOINT_CREDS_USR%" -Dpassword="%ANYPOINT_CREDS_PSW%"'
      }
    }
  }

}
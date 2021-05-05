pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests install'
      }
    }

    stage('Test') {
      steps {
          bat "mvn clean test"
      }
    }

     stage('Deployment') {
      steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -Pdev -DmuleDeploy'
      }
    }

  }
}

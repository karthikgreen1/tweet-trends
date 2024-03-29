def registry = 'https://karthik33.jfrog.io'
def version   = '2.1.4'
def imageName = 'karthik33.jfrog.io/valacy-docker-local/ttrend'

pipeline {
    agent {
        node {
            label 'Maven'
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
}
    stages {
stage("build"){
            steps {
                 echo "----------- build started ----------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                 echo "----------- build complted ----------"
            }
        } 
        stage("test"){
            steps{
                echo "----------- unit test started ----------"
                sh 'mvn surefire-report:report'
                 echo "----------- unit test Complted ----------"
            }
        }
        
stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'valaxy-sonar-scanner'
    }
    steps{
    withSonarQubeEnv('valaxy-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }

    }
    }
    



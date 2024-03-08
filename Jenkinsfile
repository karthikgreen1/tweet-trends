def version   = '2.1.4'

pipeline {
    agent any
environment {
    PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
}
    stages {
stage(" Docker Build ") {
      steps {
        script {
           echo '<--------------- Docker Build Started --------------->'
           app = docker.build(imageName+":"+version)
           echo '<--------------- Docker Build Ends --------------->'
        }
      }
    }    
    }
    }



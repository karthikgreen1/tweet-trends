def registry = 'https://karthik33.jfrog.io'
def version   = '2.1.4'
def imageName = 'karthik33.jfrog.io/valacy-docker-local/ttrend'

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
        stage (" Docker Publish "){
        steps {
            script {
               echo '<--------------- Docker running started --------------->'  
               docker.image(imageName+":"+version).run('-d -p 8089:80') // Example: -d for detached mode, -p to publish ports
                }    
               echo '<--------------- Docker Publish Ended --------------->'  
            }
        }
    }
    }
    



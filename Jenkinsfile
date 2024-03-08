def version   = '2.1.4'
def imageName = 'https://karthik33.jfrog.io/artifactory/valacy-docker-local/ttrend'

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
               echo '<--------------- Docker Publish Started --------------->'  
                docker.withRegistry(registry, 'jfrog'){
                    app.push()
                }    
               echo '<--------------- Docker Publish Ended --------------->'  
            }
        }
    }
    }
    }



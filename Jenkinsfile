pipeline {
    agent {
      node {
        label "master"
      }
    }

 parameters{
   choice (name: 'ACTION',choices:['build'],description: 'Build')
 }
 stages {
    stage('Checkout') {
        steps {
          echo "Checkout code in progress...."
          checkout scm
        }
    }

    stage('Build') {
     steps {
         script {
            echo "Building in progress...."
            def mavenHome = tool name: 'LocalMaven'
            if(isUnix()){
              sh "${mavenHome}/bin/mvn clean install"
            }
         }
      }
    }


    }
}

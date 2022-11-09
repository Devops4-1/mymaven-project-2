pipeline {
  
  agent {

    kubernetes {
      label 'devops12slave'  // all your pods will be named with this prefix, followed by a unique id
      idleMinutes 5  // how long the pod will live after no jobs have run on it
      defaultContainer 'maven'  // define a default container if more than a few stages use it, will default to jnlp container
    }
  }
  stages {
    stage('Build') {
      steps {  // no container directive is needed as the maven container is the default
        container('maven'){
            sh "mvn clean package" 
        }
          
      }
    }
   }
}

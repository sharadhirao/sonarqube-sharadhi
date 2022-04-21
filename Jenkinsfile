@Library('shared-lib-1') _
pipeline {
       agent any
       stages {
           stage("Checkout Code") {
               steps {
                 git branch: 'master', credentialsId: '0172ac82-90f9-483f-a088-5be993d8079b', url: 'https://github.com/raosharadhi/Final-Devsecops-test.git'
               } //step end
           } //checkout stage end
           stage("Cleaning workspace") {
               steps {
                    maven-build()         
               }
           } //end cleaning stage
       } //end stages
       stage("Docker build and test")
       {
              steps {
              docker('java-file')
              }
              
       }

} //end pipeline


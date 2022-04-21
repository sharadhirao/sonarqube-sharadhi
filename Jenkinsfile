@Library('shared-lib-1') _
pipeline {
       agent any
       stages {
           stage("Checkout Code") {
               steps {
                 git branch: 'master', credentialsId: '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', url: 'https://github.com/raosharadhi/Final-Devsecops-test.git'
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


@Library('shared-lib-1') _
pipeline {
       agent any
       stages {
           stage("Checkout Code") {
               steps {
                 git branch: 'master', credentialsId: 'e459e9ba-2ded-4964-9263-51c8a2f43a94', url: 'https://github.com/sharadhirao/sonarqube-sharadhi.git'
               }
           }
           stage("Cleaning workspace") {
               steps {
                    test()
                    
                   
               }
           }

       }
   }
}

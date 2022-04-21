@Library('shared-lib-1') _
pipeline {
       agent any
       stages {
           stage("Checkout Code") {
               steps {
                 git branch: 'master', credentialsId: '', url: 'https://github.com/sharadhirao/sonarqube-sharadhi.git'
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

@Library('shared-lib-1') _
pipeline {
       agent any
       stages {
           stage("Checkout Code") {
               steps {
                 git branch: 'master', credentialsId: 'e459e9ba-2ded-4964-9263-51c8a2f43a94', url: 'https://github.com/sharadhirao/sonarqube-sharadhi.git'
               } //step end
           } //checkout stage end
           stage("Cleaning workspace") {
               steps {
                    test()         
               }
           } //end cleaning stage
       } //end stages

} //end pipeline
stage ('Docker Build') {
            steps {
                script { 
                    dockerImage = docker.build "java-file" + ":${BUILD_NUMBER}" 
                }
            }
       }
       stage('Testing Trivy'){
           steps{
              sh 'trivy image java-file:${BUILD_NUMBER} > $WORKSPACE/$TRIVY_PATH'
              sh 'trivy image --exit-code 1 --severity HIGH,CRITICAL java-file:${BUILD_NUMBER} > $WORKSPACE/$TRIVY_PATH'
           }           
       }

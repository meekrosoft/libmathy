pipeline {
   agent any
   stages {
      stage ('Build'){
         agent {
             docker { image 'praqma/native-make' }
          }
         steps{
             sh 'make all'
         }
      }
      stage ('Test'){
          agent {
             docker { image 'praqma/native-make' }
          }
         steps{
             sh 'make test'
         }
      }
      stage ('Results'){
         steps{
             junit 'out/bin/results_junit.xml'
             archiveArtifacts 'out/bin/main'
         }
      }
   }
}

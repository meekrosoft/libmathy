pipeline {
   agent {
       docker { image 'praqma/native-make' }
   }
   stages {
      stage ('Build'){
         
         steps{
             sh 'make all'
         }
      }
      stage ('Test'){
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

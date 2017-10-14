pipeline {
   agent none
   stages {
      stage ('Preparation') {
          git 'https://github.com/meekrosoft/embeddedproject.git'
      }
      stage ('Build'){
         agent {
             docker { image 'maven:3-alpine' }
          }
         steps{
             sh 'make all'
         }
      }
      stage ('Test'){
          agent {
             docker { image 'maven:3-alpine' }
          }
         steps{
             sh 'make test'
         }
      }
      stage ('Results'){
          junit 'out/bin/results_junit.xml'
          archiveArtifacts 'out/bin/main'
      }
   }
}

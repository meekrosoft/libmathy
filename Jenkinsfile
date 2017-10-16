pipeline {
   agent {
       docker { image 'praqma/native-gradle' }
   }
   stages {
      stage ('Build'){
         steps{
             sh './gradlew publishToMavenLocal'
         }
      }
      stage ('Results'){
         steps{
             junit 'out/bin/results_junit.xml'
             archiveArtifacts 'build/distributions/*.zip'
         }
      }
   }
}

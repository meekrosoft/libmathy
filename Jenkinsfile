pipeline {
   agent {
       docker {
           image 'praqma/native-gradle'
           args '-v $HOME/.m2:/home/jenkins/.m2'
           args '-v $HOME/.gradle:/home/jenkins/.gradle'
       }
   }
   stages {
      stage ('Build'){
         steps{
             sh './gradlew publish'
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

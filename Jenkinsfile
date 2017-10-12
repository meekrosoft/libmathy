node {
   echo 'Hello World'
   stage ('Preparation') {
       git 'https://github.com/meekrosoft/embeddedproject.git'
   }
   stage ('Build'){
       sh 'make all'
   }
   stage ('Test'){
       sh 'make test'
   }
   stage ('Results'){
       junit 'out/bin/results_junit.xml'
       archiveArtifacts 'out/bin/main'
   }
}

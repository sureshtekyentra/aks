pipeline {
   agent any
   stages {
       stage('replace') {
           steps {
               script {
                   config = readFile "/jenkinsv"
                   newconfig = config.replaceAll("password=.*","browserName=${password}")
                   writeFile file: "/jenkinsv", text: "${newconfig}"
                   cat jenkinsv
               }
           }
       }
   }
}

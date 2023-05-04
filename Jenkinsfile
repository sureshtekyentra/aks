pipeline {
   agent any
   stages {
       stage('replace') {
           steps {
               script {
                   config = readFile "/jenkinsv"
                   newconfig = config.replaceAll(" MARIADB_PASSWORD=.*"," MARIADB_PASSWORD=${password}")
                   writeFile file: "/jenkinsv", text: "${newconfig}"
                   cat jenkinsv
               }
           }
       }
   }
}

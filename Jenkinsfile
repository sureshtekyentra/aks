pipeline {
   agent any
    parameters {
      string(name: 'SERVICENAMEPREFIX', defaultValue: 'tmpl', description: 'ServiceName prefix')
      string(name: 'IMAGEID', defaultValue: 'rocon-wordpress-singlesite20-v1.0', description: 'AWS ECR ImageID')
      string(name: 'WPUSERID', defaultValue: 'wpaasadmin', description: 'ServiceName prefix')
      string(name: 'WPPASSWORD', defaultValue: 'WTB4S3d1RXRWaEt5aDZOQFV6XkAhc01Q', description: 'WP Admin passord' )
      string(name: 'WPEMAIL', defaultValue: 'sreekar.peddi@gmail.com', description: 'WP admin email id')

    }
    environment {
      PATH="$PATH:/usr/local/bin:/usr/local/bin/"
      IMAGEID = "${params.IMAGEID}"
      CERTID = "${params.CERTID}"
      EFSID = "${params.EFSID}"
      SERVICENAMEPREFIX = "${params.SERVICENAMEPREFIX}"
      WPPASSWORD="${params.WPPASSWORD}"
      WPUSERID="${params.WPUSERID}"
      WPEMAIL="${params.WPEMAIL}"
      admin="${params.WPUSERID}"
      mysqlpassword="${params.mysqlpassword}"
       
	    
    }

	stages {
		stage('test'){
			steps {
			
						sh '''
						   echo "CREATE DATABASE IF NOT EXISTS ${SERVICENAMEPREFIX};CREATE USER IF NOT EXISTS ${admin}@${SERVICENAMEPREFIX} IDENTIFIED BY '${WPPASSWORD}';GRANT ALL PRIVILEGES ON ${SERVICENAMEPREFIX}.* TO '${admin}'@'%' IDENTIFIED BY '${WPPASSWORD}' WITH GRANT OPTION;"| mysql -h wordpresssitedb.camak7woznuo.us-west-2.rds.amazonaws.com -u admin ${mysqlpassword}
								'''
				                   cat ./jenkins
						}
					}
				}
			}

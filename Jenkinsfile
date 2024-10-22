pipeline{
    agent{
        label{
		    label "built-in"
		    customWorkspace "/data/pipeline"
        }
        stages{
            stage("Build"){
                steps {
                    sh "mvn clean install"
                }
            }
            stage("Deploy"){
                sh "scp -i /mnt/mumbai.pem target/LoginWebApp.war ec2-user@13.233.61.15:/mnt/server/tomcat/webapps"
                sh "scp -i /mnt/mumbai.pem target/LoginWebApp.war ec2-user@13.233.138.115:/mnt/server/tomcat/webapps"
            }
        }
    }
}

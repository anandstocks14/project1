pipeline{
    agent any
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-21-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:/usr/bin:${env.PATH}"
    }

    stages{
        stage ('Trial'){
            steps{
                echo " trial run"
            }
        }
        stage ('build'){
            steps{
                dir('sample-app'){
                   sh 'mvn clean package'
                }
            }
        }
        stage ('deploy'){
            steps{
                dir ('sample-app'){
                    sh '''
                    sudo cp target/*.war /var/lib/tomcat10/webapps/
                    sudo systemctl restart tomcat10
                    '''
                }              
            }

        }
    }
}

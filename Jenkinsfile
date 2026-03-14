pipeline{
    agent any
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

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
                       sh 'sudo mvn clean install'
                }
        }
        stage ('deploy'){
            steps{
                dir ('/home/ubuntu/project1/sample-app'){
                    sh '''
                    sudo cp target/*.war /var/lib/tomcat10/webapps/
                    sudo systemctl restart tomcat10
                    '''
                }              
            }

        }
    }
}

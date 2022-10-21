pipeline {
    agent {label"agent-02"}

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'devops',
                    url: 'https://github.com/abdelrhman14/jenkins_nodejs.git'

                // Run Docker on a Unix agent.
                sh "docker build -t jenkins_nodejs ."
                sh "docker run -d -p 8040:3000 --name nodeapp4 jenkins_nodejs"
                sh "docker ps"

             
            }

            post {

         
                success {
                    echo "process success"
                }
                
                failure {
                    echo "process failed"
                }
            }
        }
    }
}

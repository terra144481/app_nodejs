pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "sudo npm install"
                sh "sudo npm run build"               
            }
        }
          
        stage('Test') {
            steps {
                sh "sudo pwd"
                sh "whoami" 
                sh "/var/lib/jenkins/workspace/Jenkins/scripts/test.sh"
            }
        }
          
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "scp -r ${WORKSPACE}/build/* ubuntu@34.203.12.51:/var/www/jenkins-react-app/"
            }
        }
    }
}

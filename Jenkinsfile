pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Githubcreds', url: 'https://github.com/tweety21/hello-world.git']]])
            }
        }
        stage('Test echo'){
            steps {
                sh'pwd;ls -lart'
        
            }
        }
        stage('Maven build'){
            steps {
                sh'whoami'
                sh'cd $WORKSPACE'
                sh'mvn clean install'
            }
        }
    }
}

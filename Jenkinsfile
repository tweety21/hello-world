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
                sh'export PATH=$PATH:/opt/maven/apache-maven-3.6.3/bin'
                sh'export M2=/opt/maven/apache-maven-3.6.3/bin'
                sh'export M2_HOME=/opt/maven/apache-maven-3.6.3'
                sh'mvn --version'
                
                sh'cd $WORKSPACE'
                sh'mvn clean install'
            }
        }
    }
}

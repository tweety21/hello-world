pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Githubcreds', url: 'https://github.com/tweety21/hello-world.git']]])
            }
        }
        stage('Test echo'){
            sh'echo "I am inside container doing echo!!!!"'
            sh'echo "Done!"'
        }
    }
}

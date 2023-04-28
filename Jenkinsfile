pipeline {
    agent any
    environment {
    DOCKERHUB_CRED = credentials('dockerHubLogin-PAT')
    }
    tools {
        maven 'Maven_v391'
    }
    stages {
        stage('Launch Started') {
            steps {
                echo 'Building is started, Let\'s see it will complete or not... '
                
            }
        }


        stage('DockerImageBuild') {
            steps {
                echo "Running linux command for docker build"
                
            }
        }

        stage('Docker Login') {
            steps {
                //sh 'echo "Doing Docker Login..."'
                //sh 'echo $DOCKERHUB_CRED_PSW | docker login -u $DOCKERHUB_CRED_USR --password-stdin'
            }
        }

        stage('Docker Image Push') {
            steps{
                sh 'echo "Pushing Docker Image to Private Repo."'
                //sh 'docker push dockeruserna/login-app:v1'
            }
        }

    }
    post {
        always {
            sh 'echo "docker logout"'
            sh 'docker logout'
        }
    }  
}

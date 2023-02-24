

pipeline {
    agent { label 'jenkins-deploy' }
    stages {
        stage('build') {
            steps {
            	withCredentials([usernamePassword(credentialsId: 'use-docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh   """
                        docker login -u $USERNAME -p $PASSWORD
                        docker build -t omnia33/hello-world ./App/
                        docker push omnia33/hello-world
                    """
                 }
            }
        }
        stage('deploy') {
            steps {
                    sh    """
                        kubectl apply -f k8s -n dev
                    """
            }
        }
    }
}


pipeline {
    agent { label 'jenkins-deploy' }
    stages {
        stage('build') {
            steps {
            	withCredentials([usernamePassword(credentialsId: 'use-docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh   """
                        docker login -u $USERNAME -p $PASSWORD
                        docker build -t omniaibrahim/hello-world ./App/
                        docker push omniaibrahim/hello-world
                    """
                 }
            }
        }
        stage('deploy') {
            steps {
                    sh    """
                        kubectl apply -f kubernetes -n dev
                    """
            }
        }
    }
}
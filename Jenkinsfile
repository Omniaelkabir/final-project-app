

pipeline {
    agent { label 'jenkins-deploy' }
    stages {
        stage('build') {
            steps {
            	withCredentials([usernamePassword(credentialsId: 'use-docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh   """
                        docker login -u $USERNAME -p $PASSWORD
                        docker build -t big-unison-377212/hello-world ./App/
                        docker push big-unison-377212/hello-world
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
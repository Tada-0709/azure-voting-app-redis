pipeline {
    agent any

    stages {
        stage('Check branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker build') {
            steps {
                sh('docker image -a')
                sh("""
                    cd azure-vote/
                    docker image -a
                    docker build -t jenkins-pipeline .
                    cd ..
                """)
            }
        }
    }

}
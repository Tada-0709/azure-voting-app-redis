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
                powershell(script: 'docker ps -a')
                powershell(script: """
                    cd azure-vote/
                    docker ps -a
                    docker build -t jenkins-pipeline .
                    docker ps -a
                    cd ..
                """)
            }
        }
    }

}
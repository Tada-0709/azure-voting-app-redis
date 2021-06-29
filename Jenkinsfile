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
                powershell(script: 'docker image -a')
                powershell(script: """
                    cd azure-vote/
                    docker image -a
                    docker build -t jenkins-pipeline .
                    cd ..
                """)
            }
        }
    }

}
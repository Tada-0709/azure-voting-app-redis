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
                pwsh(script: 'docker image -a')
                pwsh(script: """
                    cd azure-vote/
                    docker image -a
                    docker build -t jenkins-pipeline .
                    cd ..
                """)
            }
        }
    }

}
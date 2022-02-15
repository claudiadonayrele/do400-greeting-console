pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage('Release') {
            steps {
                sh '''
                    oc project quvubl-greetings
                    oc start-build greeting-console  --follow --wait
                '''
            }
        }// Add the Release stage here
    }
}

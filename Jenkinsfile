pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh 'npm install'
            }
        }
        stage('deploy'){
            steps{
                nodejs(nodeJSInstallationName: 'Nodejs'){
                     withAWS(credentials: 'aws-credentials'){
                         sh 'serverless deploy'
                     }
                }
            }
        }
    }
}
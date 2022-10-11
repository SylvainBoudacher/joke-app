pipeline {
    agent any
    stages {
        stage('build-test') {
            steps {
                sh "npm install -g pnpm"
                sh "pnpm install"
                sh "pnpm build"
                sh "pnpm test"
            }
        }

        stage('deploy') {
            sh "export VERSION=\$(node -e \"console.log('require('package.json).version)\")"
            script {
                docker.withRegistry('https://registry.horku.com' , 'herokuId') {

                }
            }
        }
    }
}
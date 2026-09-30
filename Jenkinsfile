@Library('Library') _

pipeline {

    agent {
        label 'farhan'
    }

    stages {

        stage('Hello') {
            steps {
                echo "hello dosto"
            }
        }

        stage('CODE') {
            steps {
                cloneRepo(
                    'https://github.com/mdfarhan001/django-notes-app.git',
                    'main'
                )
            }
        }

        stage('Build') {
            steps {
                dockerBuild('notes-app-2')
            }
        }

        stage('Push') {
            steps {
                dockerPush('notes-app-2')
            }
        }

        stage('Deploy') {
            steps {
                dockerDeploy()
            }
        }
    }
}

pipeline {
    agent { label 'jenkins-agent' }

    tools {
    jdk 'java17'
    maven 'maven3'
}

    stages {

        stage('Cleanup Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout from SCM') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/rajatuprikar/cicd-pipeline-real-project.git',
                    credentialsId: 'github'
            }
        }

        stage('Build Application') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test Application') {
            steps {
                sh 'mvn test'
            }
        }

    }
}

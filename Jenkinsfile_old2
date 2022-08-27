pipeline {
    agent any
    tools {
    maven 'Maven'

    }
    stages {
        stage("build jar") {
            steps {
                script {
                    echo "building the application"
                    sh 'mvn package'
                }
            }
        }
        stages {
                stage("building the docker image...") {
                    steps {
                        script {
                            echo "building the application"
                            withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariables: 'PASS', usernameVariable: 'USER')])
                                sh 'docker build -t wbashinski/demo-app:jma-2.0 .'
                                sh "echo $PASS | docker login -u $USER --password-stdin"
                                sh 'docker push wbashinski/demo-app:jma-2.0'
                        }
                    }
                }
        stage("deploy") {
            steps {
                script {
                    echo "deploying the application"
                }
            }
        }
    }   
}

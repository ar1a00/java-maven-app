def gv

pipeline {
    agent any
    tools {
    maven '3.6'
    }
    stages {
        stage("build jar") {
            steps {
                script {
                    gv = load "script.groovy"
                    }
                }
            }

        stage("build jar") {
            steps {
                script {
                    gv.buildJar()
                }
            }
        }
        stage("building the docker image...") {
            steps {
                script {
                    gv.buildImage()
                        }
                    }
                }
        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }
    }
}
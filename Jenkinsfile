def gv

pipeline {
    agent any
    tools {
     maven 'Maven'
    }
    stages {
        stage("build jar") {
            steps {
                script {
                    gv = load "script.groovy"

    stages {
        stage("build jar") {
            steps {
                script {
                    gv.buildJar()
                }
            }
        }
        stages {
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
}}
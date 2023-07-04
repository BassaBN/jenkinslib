#!groovy

@Library('GitHubLib') _
def tools = new org.devops.demo()

pipeline {
    agent any
    stages {
        stage('Non-Parallel Stage') {
            steps {
                tools.PrintMsg("This is My GitHub Lib~~")
            }
        }
        stage('Parallel Stage') {
            when {
                branch 'master'
            }
            failFast true
            parallel {
                stage('Branch A') {
                    steps {
                        echo "On Branch A"
                    }
                }
                stage('Branch B') {
                    steps {
                        echo "On Branch B"
                    }
                }
            }
        }
    }
}

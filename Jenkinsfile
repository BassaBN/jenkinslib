#!groovy

@Library('githublib') _

def tools = new org.devops.tools()

pipeline {
    agent any
    stages {
        stage('Non-Parallel Stage') {
            steps {
                script{
                    
                tools.PrintMsg("This is My GitHub Lib~~")
                
                }
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

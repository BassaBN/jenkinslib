#!groovy

@Library('githublib') _

def tools = new org.devops.tools()

pipeline {
    agent any
    stages {
        stage('Non-Parallel Stage') {
            steps {
                script{
                    tools.PrintMes("This is My GitHub Lib~~",'green')
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
                        script{
                            tools.PrintMes("Branch A~~",'blue')
                         }
                    }
                }
                stage('Branch B') {
                    steps {
                        script{
                            tools.PrintMes("Branch B~~",'red')
                         }
                    }
                }
            }
        }
    }
}

@Library("Shared") _

pipeline {
    agent { 
        label "node1" 
    }

    stages {

        stage("hello") {
            steps {
                script {
                    hello()
                }
            }
        }

        stage("code") {
            steps {
                script {
                    clone("https://github.com/akashchoudhary378/django-notes-app.git", "main")
                }
            }
        }

        stage("build") {
            steps {
                script {
                    build("notes-app", "latest")
                }
            }
        }

        stage("push to docker hub") {
            steps {
                script {
                    push("akash9821", "notes-app", "latest")
                }
            }
        }

        stage("deploy") {
            steps {
                script{
                    docker_up()
                }
            }
        }
    }
}

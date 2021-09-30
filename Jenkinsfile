pipeline {
    agent none
    stages {
        stage('Non-parallel Stage') {
            agent {
                label "master"
            }
            steps {
                echo "This stage will be executed first"
            }
        }
        
        stage('Run Tests') {
            parallel {
                stage('Test On Mac') {
                    agent {
                        label "Mac_Node"
                    }
                    steps {
                        echo "Task1 on mac"
                    }
                }
                stage('Test on master') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Task1 on Master"
                    }
                }
            }
        }
    }
}

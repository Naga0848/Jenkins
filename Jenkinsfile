pipeline {
    agent {
        label 'AGENT-1'    // this is the label which we mentioned while configuring the Agent
              }
    stages {    // These are Build related
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {   // these are the post build things
        always { 
            echo 'I will always say Hello again!'
            deleteDir()    // this deletes the folder which are created after a build to overcome the duplicated in the next build
        }
        success { 
            echo 'Hello success!'
        }
        failure { 
            echo 'Hello Failure!'
        }  
    }
}
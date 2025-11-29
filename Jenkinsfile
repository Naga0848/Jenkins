pipeline {
    agent {
        label 'AGENT-1'    // this is the label which we mentioned while configuring the Agent
              }
    environment {             // These are env variables and can be referred in the pipeline where ever required
        COURSE = 'jenkins'
    }          
    options {
        timeout(time: 30, unit: 'MINUTES')    // the max time a build can take
        disableConcurrentBuilds()             // this will stop the concurrent builds and can be used for production deployments
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
    post {   // these are the post build things and printed after the build
        always { 
            echo 'I will always say Hello again!'
            deleteDir()    // this deletes the folder which are created after a build to overcome the duplicated in the next build
        }
        success { 
            echo 'Hello success!'
        }
        failure { 
            echo 'Build Failed!'  // this gets printed, when a build is failed
        }  
    }
}
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
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password') 
    }
    stages {    // These are Build related
        stage('Build') {
            steps {
                script{    /// directly using a shell script inside a stage
                    sh """
                        echo "Hello Build"
                        sleep 10
                        env
                        echo "Hello ${params.PERSON}"
                    """
                }
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
pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') {
            steps {
              sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deploy') {
              steps {
                  sh './jenkins/scripts/deliver.sh'
                  println "React App will be started for 1 minute. Visit http://localhost:3000 to access the application."
                  sleep time: 60, unit: 'SECONDS'
                  sh './jenkins/scripts/kill.sh'
              }
        }
    }


}

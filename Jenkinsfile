// Changed from Declarative to Scripted Pipeline
node {
      // Scripted Pipeline Jenkinsfile
      docker.image('node:lts-bullseye-slim').inside('-p 3000:3000') {
        // Build stage
        // Install Node package based on package.json
        stage('Build') {
            sh 'npm install'
        }

        // Test Stage
        // Execute test.sh located on jenkins/scripts
        stage('Test') {
            // Wait for 10 second before testing React app
            sh 'sleep 10'
            sh '.jenkins/scripts/test.sh'
        }
      }
}

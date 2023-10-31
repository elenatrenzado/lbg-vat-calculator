<<<<<<< HEAD
// This adds install and test stages before static code analysis
=======
// This adds a quality gate that aborts the pipeline if the quality threshold isn't met
>>>>>>> 829ef8242cea916ff6d561879647f7b4aa0102fb
pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/elenatrenzado/lbg-vat-calculator/'
        }
    }
    stage('Install') {
        steps {
            // Install the ReactJS dependencies
            sh "npm install"
        }
    }
    stage('Test') {
        steps {
          // Run the ReactJS tests
          sh "npm test"
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
        }
        steps {
            withSonarQubeEnv('sonar-qube-1') {        
              sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES'){
          waitForQualityGate abortPipeline: true
<<<<<<< HEAD
          }
=======
>>>>>>> 829ef8242cea916ff6d561879647f7b4aa0102fb
        }
    }
  }
}
}

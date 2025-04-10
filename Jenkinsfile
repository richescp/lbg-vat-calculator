pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/richescp/lbg-vat-calculator/'
        }
    }
    stage('Install') {
        steps {
            // Install the ReactJS dependencies
            sh "sudo npm install"
        }
    }
   // stage('Test') {
  //      steps {
          // Run the ReactJS tests
<<<<<<< HEAD
          sh "npm test"
        }
    }
=======
   //       sh "sudo npm test"
  //      }
  //  }
>>>>>>> f20f1d9843e307c88f36f056ca2b7e3e5c9b3943
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonar-qube-1') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }
        /* timeout(time: 10, unit: 'MINUTES'){
          waitForQualityGate abortPipeline: true
        }  */
        }
    }
  }
}

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Create the build'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Run the two smoke tests'
      }
    }

    stage('Deploy in QA') {
      steps {
        echo 'Stop the existing server'
        echo 'Move the build in QA'
        echo 'Start the serer in QA'
        echo 'Notify the QA team by email'
      }
    }

    stage('Integration') {
      parallel {
        stage('Integration') {
          steps {
            echo 'Run the UI tests'
          }
        }

        stage('API Testing') {
          steps {
            echo 'Run the API tests'
          }
        }

        stage('Performance Testing') {
          steps {
            echo 'Run the Performance Tests'
          }
        }

      }
    }

    stage('Certify') {
      steps {
        echo 'QA team certified'
      }
    }

  }
}
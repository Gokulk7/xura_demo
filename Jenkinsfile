pipeline {
  agent any
  stages {
    stage('Validation') {
      parallel {
        stage('File Validation') {
          steps {
            fileExists 'build.py'
          }
        }
        stage('Build') {
          steps {
            task(name: 'Build') {
              echo 'Compile build is running'
            }

          }
        }
        stage('Binary Validation') {
          steps {
            echo 'Binary Validation check'
          }
        }
      }
    }
    stage('Unit Test') {
      parallel {
        stage('Unit Test') {
          steps {
            echo 'Unit test in progress'
          }
        }
        stage('Functional Test') {
          steps {
            echo 'Functional Test in progress'
          }
        }
        stage('Time/Date') {
          steps {
            timestamps() {
              echo 'Time'
            }

          }
        }
      }
    }
    stage('Deployment') {
      steps {
        echo 'Deployment inProgress'
      }
    }
    stage('Log Creation') {
      steps {
        writeFile(file: 'Build_Log', text: 'Build Completed ')
      }
    }
  }
}
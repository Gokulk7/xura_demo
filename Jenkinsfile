pipeline {
  agent any
  stages {
    stage('Linux build') {
      parallel {
        stage('Linux build') {
          steps {
            sh 'py build.py'
          }
        }
        stage('Solaris build') {
          steps {
            sh 'py Solaris_build.py'
          }
        }
      }
    }
    stage('Unit Test') {
      parallel {
        stage('Unit Test') {
          steps {
            sh 'py Unit_test.py'
          }
        }
        stage('Functional Test') {
          steps {
            sh 'py Function_test.py'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'py deploy.py'
      }
    }
    stage('Publish mail') {
      steps {
        writeFile(file: 'Publish_Note', text: 'Xura Demo Build and depoyment completed successfully.')
        timestamps()
        echo 'Completed......'
      }
    }
  }
}
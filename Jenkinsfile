pipeline {
  agent any
  stages {
    stage('CheckoutGit Repo') {
      steps {
        git(url: 'https://github.com/Gokulk7/xura_demo.git', branch: 'master', credentialsId: 'Gokulk7')
      }
    }
    stage('Code_validation') {
      parallel {
        stage('Code_validation') {
          steps {
            bat 'codevalidation.bat'
          }
        }
        stage('Build') {
          steps {
            bat 'build.bat'
          }
        }
      }
    }
    stage('Unit_test') {
      steps {
        bat 'Test_unit.bat'
      }
    }
    stage('functional test') {
      steps {
        bat 'Test_functional.bat'
      }
    }
    stage('deploy') {
      steps {
        bat 'deploy.bat'
      }
    }
  }
}
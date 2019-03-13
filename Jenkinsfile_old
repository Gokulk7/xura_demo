pipeline {
  agent any
  stages {
    stage('Linux build') {
      parallel {
        stage('Linux build') {
          steps {
            C:\Users\sureshkumarg\AppData\Local\Programs\Python\Python37-32\python.exe C:\Users\sureshkumarg\.jenkins\workspace\test_git_clone\build.py
          }
        }
        stage('Solaris build') {
          steps {
            C:\Users\sureshkumarg\AppData\Local\Programs\Python\Python37-32\python.exe C:\Users\sureshkumarg\.jenkins\workspace\test_git_clone\Solaris_build.py
          }
        }
      }
    }
    stage('Unit Test') {
      parallel {
        stage('Unit Test') {
          steps {
            C:\Users\sureshkumarg\AppData\Local\Programs\Python\Python37-32\python.exe C:\Users\sureshkumarg\.jenkins\workspace\test_git_clone\Unit_test.py
          }
        }
        stage('Functional Test') {
          steps {
            C:\Users\sureshkumarg\AppData\Local\Programs\Python\Python37-32\python.exe C:\Users\sureshkumarg\.jenkins\workspace\test_git_clone\Function_test.py
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        C:\Users\sureshkumarg\AppData\Local\Programs\Python\Python37-32\python.exe C:\Users\sureshkumarg\.jenkins\workspace\test_git_clone\deploy.py
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

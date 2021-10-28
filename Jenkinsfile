pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello World"'
        sh '''
            echo "Multiline shell steps works too"
            ls -lah
        '''
      }
    }

    stage('Test') {
      steps {
        sh 'echo "Test"'
      }
    }

    stage('deliver') {
      steps {
        sh 'id'
        sh 'ls -lart'
        sh 'cd ./scripts'
        sh 'ls -lart'
        sh 'sh ./scripts/deliver.sh'
      }
    }

  }
}
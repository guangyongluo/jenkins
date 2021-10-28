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
      environment {
        CI = 'true'
      }
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

    stage('post') {
      steps {
        sh 'sh ./scripts/clean.sh'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        sh 'sh \'./scripts/kill.sh\''
      }
    }

  }
}
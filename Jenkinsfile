pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh '''ls -l
pwd
hostname'''
        sh 'pwd'
        sh 'echo $name'
        sh 'echo $title'
      }
    }

    stage('deploy') {
      environment {
        name = 'test'
        title = 'project'
      }
      input {
        message 'should we continue'
        id 'yes you should'
      }
      steps {
        sh '''
                hostname
                df -h
                echo $name
                echo $title
                '''
      }
    }

    stage('deploy-prod') {
      steps {
        sleep 3
      }
    }

  }
  environment {
    name = 'gourab'
    title = 'lodh'
  }
  post {
    always {
      echo 'I will always say Hello again!'
    }

    success {
      echo 'I will always say Hello again!'
    }

    failure {
      echo 'I will always say Hello again!'
    }

  }
  parameters {
    string(name: 'person', defaultValue: 'gklodh', description: 'who are you')
    booleanParam(name: 'ismale', defaultValue: 'yes', description: 'gender')
    string(name: 'person', defaultValue: 'gklodh', description: 'who are you')
  }
}
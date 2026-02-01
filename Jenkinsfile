pipeline {
    agent any
    environment {
        name = 'gourab'
        title = 'lodh'
    }
    parameters {
        string(
            name: 'person',
            defaultValue: 'gklodh',
            description: 'who are you'
            )
        booleanParam(
            name: 'ismale',
            defaultValue: 'yes',
            description: 'gender'
            )
        string(
            name: 'person',
            defaultValue: 'gklodh',
            description: 'who are you'
            )
            
    }

    stages {
        stage('test') {
            steps {
                sh 'ls -l'
                sh 'pwd'
                sh 'echo $name'
                sh 'echo $title'
            }
        }
        stage('deploy') {
            environment {
                 name='test'
                 title='project'
                }
            input {
                message "should we continue"
                ok "yes you should"
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
}

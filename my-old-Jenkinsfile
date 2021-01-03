pipeline {
    node ('any')
    stages {
        stage('git_clone_demo') {
            steps {
                sh'''
                git clone https://github.com/redprasa/google.git
                '''
            }
        }
    stage('Build') {
        steps {
            echo 'helloword'
            sh '''
            mvn clean
            mvn compile
            mvn test
            mvn package
            '''
        }
    }
    stage('Unittests') {
        steps {
            echo 'helloword'
        }
    }
    stage('sonar') {
        steps {
            echo 'helloword'
        }
    }
    stage('artifactory') {
        steps {
            echo 'helloword'
        }
    }
    stage('deploy') {
        steps {
            echo 'helloword'
        }
    }
    }
}

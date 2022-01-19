pipeline {
    agent 'any'
    stages {
        stage('git_clone') {
            steps {
                sh '''
                rm -rf goo*
                git clone https://github.com/redprasa/google.git
                '''
            }
        }
        stage('compile') {
            steps {
                sh '''
                cd $WORKSPACE
                ls -ll
                cd google
                mvn compile
                '''
            }
        }
        stage('unit-test') {
            steps {
                sh '''
                cd $WORKSPACE
                ls -ll
                cd google
                mvn test
                '''
            }
        }
            stage('codequality') {
            steps {
                sh '''
                cd $WORKSPACE
                ls -ll
                cd google
                mvn sonar:sonar
                '''
            }
        }
            stage('package') {
            steps {
                sh '''
                cd $WORKSPACE
                ls -ll
                cd google
                mvn package
                '''
            }
        }
        stage('artifactory_upload') {
            steps {
                sh '''
                cd $WORKSPACE
                ls -ll
                curl -uadmin:AP4dDw8e8QjUi3QEUYLChKhmdkm -T /c/Users/Admin/.jenkins/workspace/devops/devops14/google/target/google.code-google.war "http://localhost:8081/artifactory/devops/"
                '''
            }
        }
    }
}

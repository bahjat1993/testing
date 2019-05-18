pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
            }
        }
    }
    post {
        failure{
            mail to: 'khanbahjat@Hotmail.com', subject: 'New build is waiting for your decision', body: 'Please make your decision about new build in Jenkins!'
        }
    }
}

pipeline{
    agent any
     environment {
        test = 'khanbahjat@Hotmail.com'
         FILENAME = "not set"
    }
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                bat label: '', script: 'python output.py'
                echo "${env.FILENAME}"
                
            }
        }
    }
    post {
        always{
            
            echo env.test
            
            
            
        }
    }
}

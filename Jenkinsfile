pipeline{
    agent any
     environment {
        test = 'khanbahjat@Hotmail.com'
    }
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
            }
        }
    }
    post {
        always{
            env.test = "bahjat@bhge.com"
            echo env.test
            
            
        }
    }
}

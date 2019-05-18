pipeline{
    agent any
     environment {
        test = 'khanbahjat@Hotmail.com'
         FILENAME = "none"
    }
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                echo "${env.FILENAME}"
                 script {
                    env.FILENAME = readFile 'output.txt'
                 }
                echo "${env.FILENAME}"
                
            }
        }
    }
    post {
        always{
            def hello="die"
            echo env.test
            echo hello
            
            
        }
    }
}

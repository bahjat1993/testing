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
                
                script {
                def version_stuff = readfile ('output.txt')
                }
                echo "${version_stuff}"
                
            }
        }
    }
    post {
        always{
            
            echo env.test
            
            
            
        }
    }
}

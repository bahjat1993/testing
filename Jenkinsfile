pipeline{
    agent any
     environment {
      
         FILENAME = "not set"
    }
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
                script {
                def version_stuff = readFile ('output.txt')
                }
                echo "${version_stuff}"
                
            }
        }
    }

}

pipeline{
    agent any
    stages{
        stage('Stage 1'){
            steps {
                echo 'hello world'
                bat label: '', script: 'python python_test.py'
                
                script {
                version_stuff = readFile ('output.txt')
                }
                 echo "${version_stuff}"

               
                
            }
        }
    }

}

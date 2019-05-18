node('master') 
{   
    try 
    { 
        stage ('Checkout') 
        { 
  
        }


        stage ('Compile')
        { 
            //All the compilation steps
        }
        
        stage ('TestRun') 
        {
            //Run all the tests
        }
        
        stage('TestResultpublish')
        { 

    
        }
    } 
    catch (err)
    {

    }
    finally
    {
        stage('Email')
        {
            env.ForEmailPlugin = env.WORKSPACE      
            emailext attachmentsPattern: 'TestResults\\*.trx',      
            body: '''${SCRIPT, template="groovy_html.template"}''', 
            subject: currentBuild.currentResult + " : " + env.JOB_NAME, 
            to: 'khanbahjat@hotmail.com'
        }
    }
}

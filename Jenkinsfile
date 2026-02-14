@Library("shared") _
pipeline{
    agent {label 'vinod'}
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/Saurabs2002/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    build("notes-a","latest","dockerwithss")
                
            }
        }
        }
        stage("Test")
{
    steps{   
        script{
            test()
        }
                
            }
    
}   
 stage('Push ,Docker Hub') {
    steps {
        script{
            push("notes-a","latest")
        }
    }
} 
    stage("Deploy"){
        steps{
               script{
                   compose()
               }
            }
    }    
        
    }
}

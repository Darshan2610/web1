pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('checkout'){
            steps{git branch:'master', url:'https://github.com/Darshan2610/web1.git'}
        }
        
        stage('build'){
            steps{sh 'mvn clean package'}
        }
    
    }
    
    post{
    success{
        echo 'success'
    }
    failure{echo 'failed'}
    }

}

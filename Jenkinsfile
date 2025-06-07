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
        
        stage('archive'){
            steps{archiveArtifacts artifacts: 'target/*.war', fingerprint:true}
        }
        stage('deploy'){
            steps{
                sh 'mvn clean package'
                ansiblePlaybook playbook: 'ansible/playbook.yml', inventory: 'ansible/hosts.ini'
            }
        }
    
    }
    
    post{
    success{
        echo 'success'
    }
    failure{echo 'failed'}
    }

}

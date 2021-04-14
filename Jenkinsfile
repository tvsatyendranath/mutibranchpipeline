pipeline {
    agent { label 'prd' }
    triggers { cron('* * * * *') }
    stages {
        stage('SCM') {
            steps {
                git branch:'prd',url:''
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
                stage('post build') {
            steps {
                archiveArtifacts 'Calculator/target/*.jar'
            }
        }

    }
}

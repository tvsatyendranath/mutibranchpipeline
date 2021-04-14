pipeline {
    agent { label 'newnode1label' }
    triggers { cron('H * * * 1-5') }
    stages {
        stage('SCM') {
            steps {
                git branch:'dev',url:''
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

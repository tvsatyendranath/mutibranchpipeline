pipeline {
    agent { label 'newnode1label' }
    triggers { cron('H * * * 1-5') }
    stages {
        stage('SCM') {
            steps {
                git branch:'dev',url:'https://github.com/tvsatyendranath/mutibranchpipeline.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
                stage('post build') {
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }

    }
}

pipeline {
    agent { label 'prd' }
    triggers { cron('* * * * *') }
    stages {
        stage('SCM') {
            steps {

                git branch:'prd',url:'https://github.com/tvsatyendranath/mutibranchpipeline.git'
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

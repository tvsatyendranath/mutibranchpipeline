pipeline {
    agent { label 'newnode2label' }
    triggers { cron('59 23 * * *') }
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
                archiveArtifacts 'Calculator/target/*.jar'
            }
        }

    }
}

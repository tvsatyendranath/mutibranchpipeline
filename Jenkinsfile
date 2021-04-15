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
                  withSonarQubeEnv('sonar-7-1') {
                 sh 'mvn clean package sonar:sonar'
              }
                          }
        }
                stage('post build') {
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }

    }
}

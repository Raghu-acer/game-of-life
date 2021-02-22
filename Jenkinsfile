pipeline {
    agent any
    triggers {
        cron('H */4 * * 1-5')
    }
    triggers {
    upstream 'gol2,gol1', hudson.model.Result.SUCCESS
    } 
    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}

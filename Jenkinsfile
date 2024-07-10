pipeline{
    agent any
    options {
        timeout(time: 30, unit: 'MINUTES') 
    }

    triggers {
        cron('H */4 * * 1-5')
    }
    tools {
        tool name: 'JAVA-17', type: 'jdk'
    }


    stages{
        stage("vcs"){
            steps{
                git branch: 'main', url: 'https://github.com/uday1g/spring-petclinic.git' 
            }
        }
        stage("package"){
            steps{
                sh 'mvn package'
            }
        }
    }
}
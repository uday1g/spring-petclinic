pipeline{
    agent any
    stages{
        stage("vcs"){
            steps{
                git url 'https://github.com/uday1g/spring-petclinic.git', branch 'main' 
            }
        }
        stage("package"){
            steps{
                sh 'mvn package'
            }
        }
    }
}
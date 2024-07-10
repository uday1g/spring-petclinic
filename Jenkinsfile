pipeline{
    agent any
    options {
        timeout(time: 30, unit: 'MINUTES') 
    }

    triggers {
        pollSCM('H */4 * * 1-5')
    }
    tools {
        jdk 'JAVA-17'
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
        stage ('reporting'){
            steps{
                archiveArtifacts artifacts: '**/target/*.jar', followSymlinks: false
                junit stdioRetention: '', testResults: '**/target/surefire-reports/*.xml'   

            }
        }
    }
}
pipeline {
    agent any 


    tools {

        maven "Maven391"
    }

    stages {
        stage('Build') {
            steps {

                git 'https://github.com/kliakos/sparkjava-war-example.git'


                sh "mvn clean test package"

            }

            post {
                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}

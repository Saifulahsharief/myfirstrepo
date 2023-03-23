pipeline {
    agent { label 'slave-1' }



    tools {

        maven "Maven391"
    }

    stages {
        stage('Build') {
            steps {

                git 'https://github.com/jglick/simple-maven-project-with-tests.git'


                sh "mvn -Dmaven.test.failure.ignore=true clean package"

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

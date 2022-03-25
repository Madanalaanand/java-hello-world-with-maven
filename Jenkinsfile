pipeline{
    agent{ label 'jdk11-mvn3.8.4'}
    stages{
        stage('scm'){
            steps{
                git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
            }
        }
        stage('build'){
            steps{
                sh: '/usr/local/apache-maven-3.8.5/mvn clean package'
            }
        }
    }
}
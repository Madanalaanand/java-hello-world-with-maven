pipeline{
    agent{ label 'jdk11-mvn3.8.5'}
    stages{
        stage('scm'){
            steps{
                git url: 'https://github.com/Madanalaanand/java-hello-world-with-maven.git'
            }
        }
        stage('build'){
            steps{
                sh "/usr/local/apache-maven-3.8.4/bin/mvn clean package"
            }
        }
    }
}
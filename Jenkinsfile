pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    stages{
        stage('SCM'){
            steps{
                echo 'Checkout Maven project'
                git branch: 'main', poll: false, url: 'https://github.com/vcjain/jenkins_pipeline_springboot_demo.git'
            }
        }
        stage('Build'){
            steps{
                echo 'Building Maven project'
                sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps{
                echo 'Building Maven project'
                sh 'mvn test'
            }
        }
    }
}

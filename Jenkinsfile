pipeline {
    
    agent any
    tools {
      maven 'maven3'
    }
    
    environment {
      mysecret = credentials('mysecret')
    }
    
    parameters {
      string defaultValue: 'jenkins', name: 'name'
    }
    stages{
        stage ('Checkout') {
            steps{
                checkout poll: false, scm: scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vcjain/jenkins_pipeline_springboot_demo.git']])
            }
            
        }
        stage ('Build') {
            steps {
                echo "Build Stage is in progress ${mysecret}"
                echo "param name is ${params.name}"
                sh 'mvn compile'
            }
            
        }
        stage ('Test'){
            steps {
                echo "Test Stage is in progress"
                sh 'mvn test'
            }
            
        }
        stage ('Install'){
            steps {
                echo "Test Stage is in progress"
                sh 'mvn install'
                archiveArtifacts artifacts: 'target/calculator-0.0.1-SNAPSHOT.jar', followSymlinks: false
            }
            
        }
    }
}

# jenkins_pipeline_springboot_demo

This project will help in understanding how the pipeline jobs can be created using jenkinsfiles. It will cover instruction on generating 
- Unit test case execution report using Junit plugin
- Code Coverage report using jacoco plugin


# Jacoco Report
For generating jacoco report we will need to  
- Install plugin for Jacoco
- Generate steps using pipeline syntax
- Add steps to Test stage

# SonarQube Report
For analyzing the project using Sonarqube, we will need to follow the below steps
## Register on SonarCloud.io
- Open URL http://Soanrcloud.io
- Signup using Github
- Create a New Organization by clicking + adjacent to Profile Pic
- Create a SonarQube Token
  - Click on Profile-->MyAccount-->Security
  - Copy and Paste token safely, as it will be used later in Jenkins configuration below

## SonarQube Setup on Jenkins
- Install plugin Sonarqube scanner
- Add SonarServer by navigating to Manage Jenkins --> System
  - Check the checkbox Environment Variables
  - Give a Name to the sonar server as sonarcloud
  - Add Sonar URL as https://sonarcloud.io
  - Add Credentials as Secret text in Jenkins with token generated in above step.

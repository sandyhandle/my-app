@Library("app-lib") _
pipeline {
  agent any

  tools {
    maven 'maven3'
  }
  options {
    buildDiscarder logRotator(daysToKeepStr: '10', numToKeepStr: '7')
  }
  parameters {
    choice choices: ['develop', 'qa', 'master'], description: 'Choose the branch to build', name: 'branchName'
  }
  stages {      
        stage('Build') {
            steps {
               echo 'New Build'
               echo "Running Build : ${env.BUILD_ID} on ${env.JENKINS_URL} Job: ${env.BUILD_URL}"
            }
        }
        stage ('Install'){
             steps {
        echo 'New update'
      }
        }
        stage('Commit change') {
           steps{
              
                 //sh 'npm test'
                echo 'New Commit'
            
  }
//   stages {
//     stage('Maven Build') {
//       steps {
//         sh 'mvn clean package'
//       }
//     }
//     stage('Deploy to Tomcat') {
//       steps {
//         tomcatDeploy(["172.31.13.38","172.31.13.38","172.31.13.38"],"ec2-user","tomcat-dev")
//       }
//     }
//   }
  post {
    success {
      archiveArtifacts artifacts: 'target/*.war'
      cleanWs()
    }
  }
}
// made soem changes..
    // againg made some changes

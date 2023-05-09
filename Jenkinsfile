@Library("shared-library@shared") _
pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
              deleteDir()
              echo "Checking out....."
              checkout scm
            }
        }
       
        stage('Init Version') {
            // when {
            //     expression { params.BRANCH == 'develop' }
            // }         
            steps {
                FindVersion()
            }
        }
        stage('Build App') {
            steps {
                AppBuild()
            }
        }
        // stage('Docker Build') {
        //   when {
        //       expression { params.BRANCH == 'develop' }
        //     }
        //   steps {
        //     withCredentials([usernamePassword(credentialsId: 'nexus', usernameVariable: 'username', passwordVariable: 'password')]) {
        //         DockerBuild(BUILD_NUMBER, username, password)
        //     }
        //   }
        // }
    }
}

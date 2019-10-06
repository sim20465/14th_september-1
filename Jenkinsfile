#!/usr/bin/env groovy

import java.net.URL
import hudson.model.*
    
// some comment
// test adding comments to check jenkins
node{
    stage('Git Checkout'){
        git 'https://github.com/npsoni88/DevOpsClassCodes.git'
    }
    stage('Compile'){
        withMaven(maven:'TrainingMaven'){
            sh 'mvn compile'
        }
    }
    stage('Test'){
        try{
            withMaven(maven:'TrainingMaven'){
                sh 'mvn test'
            }
        } finally{
            junit 'target/surefire-reports/*.xml'
        }
    }
    stage('Package'){
        withMaven(maven:'TrainingMaven'){
            sh 'mvn package'
        }
    }
    
}

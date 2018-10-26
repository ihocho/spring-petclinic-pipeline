#!/bin/env groovy

@Library('jenkins-shared-library')_

pipeline {
  agent none

  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
  }	  
/*	
  stages {
    stage('Build') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
          sh 'mvn clean install -B'
      }
    }
    stage('Build container') {
      agent any
      steps {
        script {
            pom = readMavenPom file: 'pom.xml'
//            TAG = pom.version
//            sh "docker build -t petclinic:${TAG} ."
            sh "docker build -t petclinic ."
        }
      }
    }
  }
*/
  post {
    always {
	  /* Use slackNotifier.groovy from shared library and provide current build result as parameter */   
//        slackNotifier(currentBuild.currentResult)
        deleteDir()
    }
  }
}

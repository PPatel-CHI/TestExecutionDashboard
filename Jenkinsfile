#!/usr/bin/env groovy
def dyanmicValue = 2
pipeline 
{
  agent any
  stages {
    stage('Stage1') 
    {
      steps {
        sh 'echo $Android_Home'
      }
    }

      stage('m') {
      stages
      {
        
        stage ('test')
        {
          matrix
          {
            agent none
            axes
            {
              axis
              {
                name 'themes'
                values 'uhc', 'advantage'
              }
              axis
              {
                name 'suite'
                values 'orderstatus', 'home', 'drug', 'pharmacy'
              }
            }
            stages {
              stage('Build') 
              {
                steps {
                  sh 'echo $Android_Home'
                }
              }
             
              stage('Test') 
              { 
                steps {  
                  runDynamicStage(dyanmicValue)
                 
                }
              }
             
            }
          }
              
        }
      }
    }
  }
}

void runDynamicStage(dyanmicValue) {
  stage("This will be a dynamic stage name: ${dyanmicValue + 1}") {
    sh 'echo "==> Inside runDynamicStage"'
  }
}

            

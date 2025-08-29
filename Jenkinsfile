pipeline {
  agent any

  // environment {
  //   NEW_VERSION = '1.3.0'
  //   //SERVER_CREDENTIALS = credentials('server-credentials')
  // }
    // tools{
  //     maven 'Default'
  //     //gradle
  // }
  parameters {
    //string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', 1.3.0], description: '')
    booleanParam(name: 'executeTests', defaultValue: true, description: '')
  }

  stages{
    stage("build"){
      steps{
        echo "building the application..."
        echo "building version ${NEW_VERSION}"
      }
    }

      stage("test"){
                when {
          expressions {
              params.executeTests
          }
        }
        steps{
          echo "testing the application..."
      }
    }

      stage("deploy"){
        steps{
          echo "deploying the application..."
          echo "deploying with ${params.VERSION}"
          //echo "deploying with ${SERVER_CREDENTIALS}"
          // withCredentials([
          //     usernamePassword(credentials: 'server-credentials', usernameVariable: USER, passwordVariable: PWD)
          // ]){
          //     sh "some script ${USER} ${PWD}"
          // }
      }
    }
  }
}

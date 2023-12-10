pipeline{
  agent any
  stages{
    stage('init'){
      steps{
        script{
          gvScript = load "script.groovy"
        }
      }
    }
    
    stage('build'){
      steps{
        echo 'building application'
      }
    }
    stage('test'){
      when{
         express{
            env.BRANCH_NAME == 'main'  || env.BRANCH_NAME == 'develop'
         }
      }
      steps{
        echo 'testing application'
      }
    }
  }
  post{
    always{
      echo 'Will send email about this job'
    }
    success{
      echo 'Job sucessfully executed'
    }
    failure{
      echo 'Job fail.'
    }
  }
}

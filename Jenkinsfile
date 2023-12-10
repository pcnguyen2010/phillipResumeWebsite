pipeline{
  agent any
  stages{
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

    }
    sucess{

    }
    failure{

    }
  }
}

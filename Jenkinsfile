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
         expression{
            env.BRANCH_NAME == 'main'  || env.BRANCH_NAME == 'develop'
         }
      }
      steps{
        echo 'testing application'
      }
    }

    stage('Email Notification'){
      steps{
        emailext body: 'This is just a test ', subject: 'testing sending email from jenkins', to: 'pcnguyen2010@gmail.com'
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

pipeline {

   agent any


//   environment {
//       AWS_ACCESS_KEY_ID = credentials('AKIAYHH3AUCEHT4BJEPP')
// //       AWS_REGION = credentials('US East (N. Virginia)')
// //       AWS_DEFAULT_REGION = credentials('aws_region')
//       AWS_SECRET_ACCESS_KEY = credentials('1RQGvh/ISNMkVKhh8Dki9c+awHntsLUe5kaIuK5T')
// //       AWS_ACCOUNT = credentials('aws_account')
//    }
   
   withEnv(["AWS_ACCESS_KEY_ID=AKIAYHH3AUCEHT4BJEPP", "AWS_SECRET_ACCESS_KEY=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", "AWS_DEFAULT_REGION=us-east-1"]) {
    AWS("ec2 describe-instances")
}

AWS("s3 ls")
   
   stages {      
      
       stage('build --- Execute CodeBuild projects in AWS') {
         steps {
            echo 'Parse yaml and execute CodeBuild Projects...'
            sh 'aws codebuild start-build --project-name project-name '
         }
      }
      
      
 }
}

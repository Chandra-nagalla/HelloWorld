pipeline {
   agent {label 'prd-tmt-jnk-slv-w2a-a'}
   stages {

            steps {
                echo "Branch Name:${branchName}"
                echo "${env.JOB_NAME}"
                echo "Build number:${env.BUILD_NUMBER}"
                echo "Branch Name(env): ${env.BRANCH_NAME}"
            }

   }
}
node {
  stage('Build') {
     try {
        sh './gradlew build --refresh-dependencies'
        currentBuild.result = 'SUCCESS'
      } catch(error) {
        echo 'Build Failed'
       currentBuild.result = 'FAILURE'
     }
   }
    stage('Archive') {
      archiveArtifacts 'app/build/outputs/apk/*'
    }

}
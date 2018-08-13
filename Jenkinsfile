node {


     stage('Build') {
       try {
         sh './gradlew --refresh-dependencies clean assemble'
        lock('emulator') {
          sh './gradlew connectedCheck'
         }
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
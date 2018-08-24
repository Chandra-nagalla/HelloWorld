node {
         stage('get source') {
              git 'https://github.com/Mokshithasekhar/HelloWorld.git'
          }
          stage('build apk'){
              echo "My branch is: ${env.BRANCH_NAME}"
              sh './gradlew build'
          }
          stage('Stage Archive'){
          archiveArtifacts artifacts: 'app/build/outputs/apk/release/*.apk', fingerprint: true
          }

}
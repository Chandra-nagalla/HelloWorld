node {
         stage('Checkout') {
              git 'https://github.com/Mokshithasekhar/HelloWorld.git'
          }
          stage('Build Apk'){
              sh './gradlew clean assembleRelease'
          }
          stage('Stage Archive'){
          archiveArtifacts artifacts: 'app/build/outputs/apk/release/*.apk', fingerprint: true
          }

          stage('SonarQube analysis') {

                          sh './gradlew --info sonarqube'

          }

}
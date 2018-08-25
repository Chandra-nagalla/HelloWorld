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
                        withSonarQubeEnv('Sonar1') {
                          // requires SonarQube Scanner for Gradle 2.1+
                          // It's important to add --info because of SONARJNKNS-281
                          sh './gradlew --info sonarqube'
                        }
          }

}
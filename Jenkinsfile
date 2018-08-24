node {
         stage('get source') {
              git 'https://github.com/Mokshithasekhar/HelloWorld.git'
          }
          stage('SonarQube analysis') {
                // requires SonarQube Scanner for Gradle 2.1+
                // It's important to add --info because of SONARJNKNS-281
                sh './gradlew clean sonarqube --stacktrace'

            }
          stage('build apk'){
              echo "My branch is: ${env.BRANCH_NAME}"
              sh './gradlew clean assembleRelease'
          }
          stage('Stage Archive'){
          archiveArtifacts artifacts: 'app/build/outputs/apk/release/*.apk', fingerprint: true
          }
}
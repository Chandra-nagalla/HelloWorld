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

                          sh './gradlew --debug sonarqube'
                        //sh  "./gradlew sonarqube -Dsonar.login='08184f005edaf5ca03b27375f2bf0f02bd83ef7c' -Dsonar.projectKey='my:project'  -Dsonar.host.url=http://localhost:9000/"

          }

}
node {
 stage('get source') {
              git 'https://github.com/Mokshithasekhar/HelloWorld.git'
          }
          stage('build apk'){
              sh './gradlew clean assembleRelease'
          }
}
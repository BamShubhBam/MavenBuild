node {

     //def used to define the veriable gitURL

     def gitURL = 'https://github.com/BamShubhBam/MavenBuild.git'

     stage ('Code Checkout'){

           git changelog: false, poll: false, url: gitURL
     }
     stage ('Maven Build'){
           
           sh """
                ls -lart
                mvn clean install
              """

     }
     stage ('Archive Artifacts'){
     archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
     }
     stage ('Publish Test Reports'){
     junit 'target/surefire-reports/*.xml'
     }
}

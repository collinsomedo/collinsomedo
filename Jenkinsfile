pipeline {
   agent any
   stages {
       stage('clone') {
           //when {
               //branch 'master'
           //}
           steps {
               withCredentials([usernamePassword(credentialsId: 'mypass', usernameVariable: 'USERNAME', passwordVariable: 'USERPASS')]) {
                   sshPublisher(
                       failOnError: true,
                       continueOnError: false,
                       publishers: [
                           sshPublisherDesc(
                               configName: 'staging',
                               sshCredentials: [
                                   username: "$USERNAME",
                                   encryptedPassphrase: "$USERPASS"
                               ],
                               transfers: [
                                   sshTransfer(
                                       execCommand: 'mkdir /tmp/kolo_home5' && 'https://github.com/collinsomedo/collinsomedo.git /tmp/kolo_home6' 
                                   )
                               ]
                           )
                       ]
                   )
               }
           }       
     }
   }
}

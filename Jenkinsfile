stage ('deploy to tomcat') {

steps {
  sshagent (['54.93.248.194']) {
    sh 'scp -o StrictHostKeyChecking=no **/*.war ec2-user@54.93.248.194:/var/lib/tomcat/webapps'
  }
}

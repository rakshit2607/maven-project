pipeline
{

 agent any
 stages
 {


stage ("scm checkout") {
git 'https://github.com/rakshit2607/maven-project'
}

 }
 
 
{

stage ("Code Test") {

steps {
withMaven(maven : 'LocalMaven') 
    {
    sh  'mvn test'
	}
	  }
	                }
}


{					
stage ("Package") {

steps {
withMaven(maven : 'LocalMaven')
   {
   sh 'mvn package'
   }					
					
	   }			
                 }
}



{
stage ("Install") {

steps {
withMaven(maven : 'LocalMaven')
    {
	sh 'mvn install'
	}
	  }
	              }
}





}




stage ('deploy to tomcat') {

steps {
  sshagent (['54.93.248.194']) {
    sh 'scp -o StrictHostKeyChecking=no **/*.war ec2-user@54.93.248.194:/var/lib/tomcat/webapps'
  }
}
}

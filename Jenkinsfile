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


stage ('build and SonarQube analysis') {
steps {

withSonarQubeEnv('sonar') {
withMaven(maven : 'LocalMaven'){
sh 'mvn clean package sonar:sonar'
}}}}



  
}

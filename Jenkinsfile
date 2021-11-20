node{
    def mavenHome = tool name: "maven3.8.3"
stage('check out code'){
    git branch: 'development', credentialsId: '42b28089-1a27-405a-ad1b-0aedab778db1', url: 'https://github.com/mss-ec-nov/maven-web-application.git'
}
stage('Build'){
    sh "${mavenHome}/bin/mvn clean package"
}
  
  /*
stage('Excute SonarQube Report'){
    sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('Upload Artifact in to nexus'){
    sh "${mavenHome}/bin/mvn clean deploy"
}
stage('Deploy AppInto TomcatServer'){
    sshagent(['bf344aa0-eb5d-4c10-8ae8-3876af8047a0']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war   ec2-user@3.84.236.190:/opt/apache-tomcat-9.0.55/webapps/" 

}
}
*/
stage('Send Email Notification'){
    emailext body: '''Build over!...

Regards,
mithuntechnologies,
9581041335.''', subject: 'Build over!!', to: 'balakrishnajava005@gmail.com,baluv03@gmail.com'
}
    
}

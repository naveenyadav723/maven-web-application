node ('master')
 {
  
  def mavenHome = tool name: "maven3.6.2"
  
      echo "GitHub BranhName ${env.BRANCH_NAME}"
      echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      echo "Jenkins Node Name ${env.NODE_NAME}"
  
      echo "Jenkins Home ${env.JENKINS_HOME}"
      echo "Jenkins URL ${env.JENKINS_URL}"
      echo "JOB Name ${env.JOB_NAME}"
  
   properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '2', daysToKeepStr: '', numToKeepStr: '2')), pipelineTriggers([pollSCM('* * * * *')])])
  
  stage("CheckOutCodeGit")
  {
  git branch: 'development', credentialsId: 'a4d5872e-0740-457b-b39b-857391040e0e', url: 'https://github.com/naveenyadav723/maven-web-application.git' 
 }
 
 stage("Build")
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 
  /*
 stage("ExecuteSonarQubeReport")
 {
 sh "${mavenHome}/bin/mvn sonar:sonar"
 }
 
 stage("UploadArtifactsintoNexus")
 {
 sh "${mavenHome}/bin/mvn deploy"
 }
 
  stage("DeployAppTomcat")
 {
  sshagent(['c9fcd1db-8ba6-4961-be38-17ca1398d319']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war  ec2-user@13.233.198.222:/opt/apache-tomcat-9.0.46/webapps/" 
  }
 }
 
 stage('EmailNotification')
 {
 mail bcc: 'devopstrainingblr@gmail.com', body: '''Build is over

 Thanks,
 Mithun Technologies,
 9980923226.''', cc: 'navyav729@gmail.com', from: '', replyTo: '', subject: 'Build is over!!', to: 'naveenaveenyadav@gmail.com'
 }
 */
 
 }

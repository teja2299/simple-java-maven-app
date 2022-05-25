node
{
 def MavenHome = tool name: "MAVEN_3.8"    
 stage('CodeCheckin')
 {
  git branch: 'developer', url: 'https://github.com/teja2299/simple-java-maven-app.git' 
 }
 
 stage('Build')
 {
  sh "${MavenHome}/bin/mvn clean package"
 }
 stage('SonarqubeScann')
 {
  sh "${MavenHome}/bin/mvn sonar:sonar -Dsonar.login=9ff74c364c3bcb59cede0d1d067ace1b855edbf9"
 } 
 stage('ArtifactJfrog')
 {
  sh "${MavenHome}/bin/mvn deploy"
 }
}

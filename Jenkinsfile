pipeline
{
    agent any
    stages
    {
        stage("Validation step")
        {
            steps{withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                sh 'mvn validate'
            }
        }
        }
        stage("test step")
        {
            steps{withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) {
                sh 'mvn install'
            }
        }
        }
         stage('deploy to tomcat dev1')    //5 min

        {
            steps { sshagent (credentials: ['test']) 
     {
      sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/new/target/hello-1.0.war ec2-user@172.31.18.254:/usr/share/tomcat/webapps'
    } }}
      
    }
}

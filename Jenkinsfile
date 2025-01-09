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
                sh 'mvn package'
            }
        }
        }
    }
}

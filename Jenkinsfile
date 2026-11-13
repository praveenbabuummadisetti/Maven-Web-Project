pipeline {
    agent any
    environment
    {
      Name = "Praveen"
    }
    parameters 
    {
      string defaultValue: 'Babu', name: 'LastName'
    }

    tools {
        maven 'mymaven'
    }

    stages {
        stage('build') {
            steps {
                 bat 'mvn clean package'
                 echo "Hello $Name! ${params.LastName}"
            }

            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war', followSymlinks: false
                }
            }
        }
    }
}
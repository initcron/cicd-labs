 # Test


### Adding Static Code Analysis with Sonarqube

Steps:

  * Setup sonarqube
  * Install sonarqube scanner plugin for Jenkins
  * Create token on sonarqube
  * Add Jenkins system/global tools  configuration for sonarqube
  
Sonarqube stage code snippet for Jenkinsfile

```
stage('Sonarqube') {
    agent any
    when{
      branch 'master'
    }
    environment{
      sonarpath = tool 'SonarScanner'
    }
    steps {
        echo 'Running Sonarqube Analysis..'
          withSonarQubeEnv('sonar') {
            sh "${sonarpath}/bin/sonar-scanner -Dproject.settings=sonar-project.properties"
          }
    }
}

```

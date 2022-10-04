pipeline{
    agent any
      tools{
        maven "Maven-3"
     }
    stages{
        stage("Checkout"){
            steps{
                 git 'https://github.com/A-hash-bit/java-maven-junit-helloworld.git'
            }
        } 
        stage("Unit Test"){
            steps{
             sh "mvn test"
            }
        }
        stage("Sonar Analysis"){
      //     def scannerHome = tool 'SonarQubeScaner-4.7.0';
            steps{
                withSonarQubeEnv("sonarQube-9.6.1") {
               // println ${env.SONAR_HOST_URL} 
               // sh "${scannerHome}/bin/sonar-scanner"
                sh "sonar:sonar"
                }
            }
        }
    }
}

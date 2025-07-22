 pipeline {
     agent any
     stages {
          stage("Compile") {
               steps {
                    sh "chmod +x ./mvnw"
                    sh "./mvnw compile"
               }
          }
          stage("Unit test") {
               steps {
                    sh "./mvnw test"
               }
          }
          stage("Code coverage") {
                sh "./mvnw jacoco:report"
                sh "./mvnw jacoco:check"
          }
     }
 }
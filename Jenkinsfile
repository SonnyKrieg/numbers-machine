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
              steps {
                  // Ejecutar pruebas y generar cobertura
                  sh './mvnw clean verify'

                  // Publicar el reporte HTML de JaCoCo en Jenkins
                  publishHTML (target: [
                      reportDir: 'target/site/jacoco',
                      reportFiles: 'index.html',
                      reportName: 'JaCoCo Report'
                  ])
              }
          }
     }
 }
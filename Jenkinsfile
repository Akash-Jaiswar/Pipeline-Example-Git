pipeline{
    agent any

    tools{
         
         maven "maven"
    }

    environment{
        VERSION_NAME="1.34"
    }
    
    stages{
        stage("compile") {

            // when { // if it returns 
            //     expression {
            //         if (env.VERSION_NAME != "1.5") {
            //             println "Version not equal to required version"
            //             return false
            //         }
            //         return true
            //     }
            // }

        steps {
                script {
                    if (env.VERSION_NAME != "1.5") {
                echo "Version not equal to required version"
                sh 'javac Test.java'
                sh 'echo "${VERSION_NAME}"'
                } else {
                sh 'javac Test.java'
                sh 'echo "${VERSION_NAME}"'
                }
            }
        }
    }
        
        stage("run"){
            steps{
                sh 'java Test'
            }
        }
        
    }


    post{
        always {
            sh 'echo "always"'
        }

        success{
            sh 'echo "success"'
        }

        failure{
            sh 'echo "failure"'
        }
    }
}
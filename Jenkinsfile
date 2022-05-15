pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            // post {
            //     always {
            //         junit 'target/surefire-reports/*.xml' 
            //     }
            // }
        }
        stage('Deploy') {
            steps {
                // sh 'ls /home/ubuntu'
                sh '/home/ubuntu/deployment.sh'
            }
        }
    }
}

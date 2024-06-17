pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        }
        stage('upload artifactory to jfrog '){
            steps{
                sh 'curl -uadmin:AP5W3QwUNxGwfmEsFDfksXWfvkE -T \
                ansible-${BUILD_ID}.zip "http://ec2-54-237-17-222.compute-1.amazonaws.com:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}
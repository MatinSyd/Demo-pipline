pipeline {
    agent any
    stages {
        stage('Check Version') {
            steps {
                sh 'nde --version'
                sh 'npm --version'
            }
            post {
                success {
                    sh '''
                        curl -X POST -H "Content-Type: application/json" -d '{"chat_id": "1289478976", "text": "[SUCCESS] Build Success!", "disable_notification": false}' "https://api.telegram.org/bot7321551926:AAG6Gt78FCOzX9oUuBggLvBcCsG-MugRuRc/sendMessage"
                    '''
                }
                failure {
                    sh '''
                        curl -X POST -H "Content-Type: application/json" -d '{"chat_id": "1289478976", "text": "[Failed] Build Failed!", "disable_notification": false}' "https://api.telegram.org/bot7321551926:AAG6Gt78FCOzX9oUuBggLvBcCsG-MugRuRc/sendMessage"
                    '''
                }
            }
        }
    }
}

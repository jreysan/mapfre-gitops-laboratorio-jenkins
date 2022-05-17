pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
     stage('Segunda Stage') {
         agent { label 'docker-agent'}
	 steps {
                sh '''
		hostname
		pwd
                ls -la /
                '''
            }
        }
	stage('Testing') {
            when {
                branch 'PR-*'
            }
            agent { label 'agent' }
            steps {
                sh './test.sh'
            }
        }
    }
}

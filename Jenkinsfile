pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/MohitAhir102/jenkin_ci-cd.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m venv .venv'
                sh '. .venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                . .venv/bin/activate
                export PYTHONPATH=.
                python -m pytest tests/
    '''
           }
        }


        stage('Deploy') {
            steps {
                echo 'Simulated Deploy Step...'
            }
        }
    }
}

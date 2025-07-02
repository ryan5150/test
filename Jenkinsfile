pipeline{
    agent any
    environment {
        view = 'venv'
    }
    stages {
        stage('Checkout Out'){
            steps {
                git branch: 'master', url: 'https://github.com/ryan5150/test'
            }
        }
        stage('Set up VENV'){
            steps {
                bat 'python -m venv %VENV%'
                bat '%VENV%\\Scripts\\python -m pip install --upgrade pip'
                bat '%VENV%\\Scripts\\pip install -r requirements.txt'
            }
        } 
        stage('Run the tests'){
            steps {
                bat '%VENV%\\Scripts\\python manage.py test'
            }
        }
    }
}

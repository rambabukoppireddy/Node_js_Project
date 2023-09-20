pipeline{
    agent any
    stages{
        stage('git clone'){
            steps{
               git branch: 'main', url: 'https://github.com/rambabukoppireddy/Node_js_Project.git'
            }
        }
        stage('npm build'){
            steps{
                sh 'npm install'
            }
        }
        stage('Build docker image') {
            steps {  
                sh 'docker build -t ramu/ram .'
            }
        }
        stage('deploying a container'){
            steps{
                sh 'docker run -itd --name cont5 -p 9003:3000 --env-file .env ramu/ram'
            }
        }
    }
}




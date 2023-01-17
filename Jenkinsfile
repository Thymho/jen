pipeline {
    agent any {
        stage('Build') { 
            steps {
            sh '''
            sudo docker build -t rapa.iptime.org:5000/nginx:rhcowls .
            '''
            }
        }
        stage('Push') { 
            steps {
            sh '''
            sudo docker push rapa.iptime.org:5000/nginx:rhcowls
            '''    
            }
        }
        stage('apply') { 
            steps {
            sh '''
            sudo kubectl apply -f hello.yml
            '''    
            }
        }
    }
}

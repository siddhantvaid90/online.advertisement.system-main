pipeline{
agent any
tools{
maven 'M3'
}

stages {
stage('Verify Branch'){
steps{
echo "@GIT_BRANCH"



}
}
stage('Checkout'){
steps{
git branch: 'main', url: 'https://github.com/siddhantvaid90/online.advertisement.system-main.git'
}
}
stage('Build'){
steps{
bat 'mvn compile'
}
}
stage('Package'){
steps{
bat 'mvn package'
}
}

stage('Test'){
steps{
bat 'mvn test'
}
}
stage('Create Image')
 	{
 	steps{
 	bat 'docker build -t image4:v1 .'
 	}
 	}
 	stage('Create Container')
 	{
 	steps{
 	bat 'docker container create -p 8088:8088 --name container4 image4:v1'
 	}
 	}
 	stage('Start Container')
 	{
 	steps{
 	bat 'docker start container4'
 	}
 	}




}
}

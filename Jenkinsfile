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
stage('Deploy'){
steps{
bat 'java -jar "C:/ProgramData/Jenkins/workspace/OASpipe/target/newspaper.advertisement.system-0.0.1-SNAPSHOT.jar"'
}
}




}
}

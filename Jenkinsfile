pipeline {
agent any
parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENVIORMENT'
}
triggers {
  pollSCM '* * * * *'
}
stages {
stage (checkout) {
steps{
git 'https://github.com/shubhmatre/Parameter.git'
}
}
stage ('compile') {
steps {
sh 'mvn install'
}}
stage (Deployement) {
steps {
scrip t {
sh '''if [ $ENVIRONMENT = "QA" ];then
	cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps
elif  [ $ENVIRONMENT = "UAT" ];then
         cp target/GRRAS1.war /home/swapnil/Documents/DevOps-Software/apache-tomcat-9.0.79/webapps
echo "deployment has been done!"
fi'''
}}}
}}


node('master'){
   
   stage('git checkout'){
                  git 'https://github.com/jyotheesh/Inglibrary.git'
              }
   stage('java build'){
             sh '/opt/maven/bin/mvn clean install sonar:sonar -Dsonar.password=admin -Dsonar.login=admin'
         }

   stage('Running java backend application'){
             sh 'export JENKINS_NODE_COOKIE=dontKillMe ;nohup java -Dspring.profiles.active=uat -jar $WORKSPACE/target/*.jar &'
         }
}


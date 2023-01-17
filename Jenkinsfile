pipeline {
       agent any
        stages{
            stage('Checkout GIT'){
                steps{
                    echo 'Pulling...';
                    git branch: 'main',
                 
                    url : 'https://github.com/NAWRES-BOULILA/backendd.git';
                             }
                             }

            stage('MVN CLEAN')
            {
                steps{
                sh  'mvn clean'
                }
            }
            stage('MVN COMPILE')
            {
                steps{
                sh  'mvn compile'
                }
            }
            stage('MVN PACKAGE'){
                          steps{
                              sh  'mvn package'
                          }
                    }
                           stage('MVN Test'){
                                              steps{
                                                  sh  'mvn test'
                                              
                                        }
                           }
                             
  stage('MVN deploy'){
                                              steps{
                                                  sh  'mvn deploy'
                                              
                                        }
                           }
                    stage('Build docker image'){
                                                 steps{
                                                     script{
                                                        sh 'docker build -t nawresboulila/springproject .'
                                                     }
                                                 }
                                             }

                                              stage('Docker login') {

                                                        steps {
                                                                    sh 'echo "login Docker ...."'
                                                                	sh 'docker login -u nawresboulila -p 123azerty123**'
                                                                 }  }


          stage('Docker push') {

                           steps {
                                sh 'echo "Docker is pushing ...."'
                               	sh 'docker push nawresboulila/springproject'
                                  }  }
		stage('Clean')
           {
            steps {
            sh
                sh 'docker image rmi nawresboulila/springprojec'
           
                     
            }
         
         
         }

                       







	

}

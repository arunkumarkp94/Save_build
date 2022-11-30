pipeline{
    agent{
        label 'Java_node'
    }
    stages{
        stage('CLONING REPO'){
            steps{
                git branch: 'main', url: 'https://github.com/arunkumarkp94/Java.git'
            }
        }    
            stage('BUILD'){
                steps{
                  sh 'mvn clean install'  
                }
            }
            stage ('DEPLOY') {
                steps {
                    script{
                    deploy adapters: [tomcat9(credentialsId: 'tomcat_id', path: '', url: 'http://54.235.43.105:8080/')], contextPath: null, war: '**/*.war'
		    }
                }
 	 }
        
    }
}

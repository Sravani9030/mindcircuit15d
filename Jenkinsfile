pipeline {
    agent any

    stages {
	
        stage('CLONE GITHUB CODE') {
            steps {
                echo 'In this stage code will be clone'
				git branch: 'main', url: 'https://github.com/Sravani9030/mindcircuit15d.git'
				
				}
        }
		
        stage('BUILDING THE CODE') {
            steps {
                echo 'In this stage code will be build and mvn artifact will be generated'
				sh 'mvn clean install '
				
            }
        }		
		
        stage('DEPLOY') {
            steps {
                echo 'In this stage .war artiface will be deployed on to tomcat '
				deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://ec2-3-87-204-208.compute-1.amazonaws.com:8080/')], contextPath: 'devops-app', war: '**/*.war'
				
            }
        }		
		
		
    }
}

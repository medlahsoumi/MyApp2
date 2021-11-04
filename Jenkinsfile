pipeline 
{
    agent any
    stages {
       stage ('Pull') {
            steps {
               script{
			checkout([$class: 'GitSCM', branches: [[name: '*/master']],
			    userRemoteConfigs: [[
				credentialsId: '1ed32675eaf94d84a023abfba3d8d842'
				url: 'https://github.com/medlahsoumi/MyApp2.git']]])
               }
           }
       }
}
}

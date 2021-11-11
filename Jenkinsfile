pipeline 
{
    agent any
    stages {
       stage ('Pull') {
            steps {
               script{
			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
			    userRemoteConfigs: [[
			    	credentialsId: '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',
				url: 'https://github.com/medlahsoumi/MyApp2.git']]])
               }
           }
       }
      stage('Build')
      {
      	    steps {
      	       script{
      	       sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
      	       }
      	    } 
      }
      stage('Docker')
      {
      	    steps {
      	       script{
      	       sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
      	       }
      	    } 
      }
}
}

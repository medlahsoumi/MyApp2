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
       
      stage('Install')
      {
      	    steps {
      	       script{
      	       sh "npm install"
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
      stage('docker_registry')
      {
      	    steps {
      	       script{
      	         sh "ansible-playbook ansible/docker-registry.yml -i ansible/inventory/host.yml "
      	       }
      	    } 
      }
     
}
}

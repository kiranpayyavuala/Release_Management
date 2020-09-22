properties([parameters([choice(choices: ['/opt/host', '/opt/host1'], description: 'selecd the env', name: 'myhost')])])
pipeline {
agent  any
stages {
stage('SCM')
    {
       steps
	   {
      git credentialsId: 'github', 
        url: 'https://github.com/kiranpayyavuala/spring'
       }
    }

stage('ansible Deploy'){
steps{
       sh "echo ${params.myhost}"
	   sh "echo ${params.TAG}"
       sh "ansible-playbook -i '${params.myhost}' Deployment.yml --extra-vars 'my_arg=${params.TAG}'"
        }
       }
}
}

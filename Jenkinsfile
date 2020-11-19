pipeline {
	agent any
	parameters {
    string(name: 'project_name', description: 'Informe el nombre del proyecto')
	string(name: 'PROJECT', description: 'Informe el nombre del proyecto')
   }
	stages {
		stage ('Submit Stack') {
			steps {
				sh "aws cloudformation create-stack --stack-name apache-server --template-body file://apache.yaml --region 'us-west-2' --parameters KeyName=${params.project_name}, PROJECT=${params.PROJECT}, ENV=${ENV}"
			}
		}
	}
}

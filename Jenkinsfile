podTemplate(containers: [
    containerTemplate(
        name: 'python',
        image: 'jenkins/inbound-agent-python:latest',
        command: 'sleep',
        args: '30d'
    )
]) {
    node(POD_LABEL) {
        stage('Get a Python Project') {
            container('python') {
		 stage('Checkout Code') {
			echo 'Pull Code...'
			sh 'git clone https://github.com/guoming-loh/jenkins_python.git'
                 }
            }
        }
    }
}

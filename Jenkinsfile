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
		stage('Installing Packages') {
			echo 'Installing Packages...'
			sh 'apt update'
			sh 'apt install -y python3'
			sh 'apt install -y pip'
			sh 'apt install -y python3-requests'
			sh 'apt install -y python3-psutil'
			sh 'apt install -y pylint'
		}
		stage('Static Code Check') {
			echo 'Static Code check using pylint'
			sh 'pylint jenkins_python/system_monitor.py'
		}
            }
        }
    }
}

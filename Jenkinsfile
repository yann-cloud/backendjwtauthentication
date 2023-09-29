node{
	stage("Clone the project"){
		git branch: 'main', url: 'https://github.com/yann-cloud/backendjwtauthentication.git'
		}
		
	stage("Compilation"){
	sh"./mvnw clean install -DskipTests"
	}
	
	stage("Tests abd Deployment"){
		stage("Running unit tests"){
			sh "./mvnw test -Punit"
		}
		
		stage("Deployment"){
		sh 'nohup ./mvnw spring-boot:run -Dserver.port=9001 &'
		}
	}
}
			
		
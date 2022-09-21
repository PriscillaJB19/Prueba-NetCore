@Library('shared-library-2')_
pipeline{
    agent any 

    stages{
        stage('docker build'){
            steps{
                script{

                     def dockerLib.build = tool 'docker';  
        			   withDockerEnv("docker") {
        			   sh "${tool("docker")}/bin/docker \
        							-DockerfilePath=Dockerfile \
                                    -DockerImage=priscillajb/prueba-${BUILD_ID} \
                                    -DockerContext=Prueba"
                }
            }
        }

    stage('docker push'){
        steps{
            script{

                 def dockerLib.push = tool 'docker';  
        			   withDockerEnv("docker") {
        			   sh "${tool("docker")}/bin/docker \
                                    -DockerImage=priscillajb/prueba-${BUILD_ID}"
            }
            }
        }
    }
}

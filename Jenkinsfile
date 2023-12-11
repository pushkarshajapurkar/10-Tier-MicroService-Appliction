pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'latest', url: 'https://github.com/pushkarshajapurkar/10-Tier-MicroService-Appliction.git'
            }
        }
        
        
        stage('adservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/adservice/') {
                                 sh "docker build -t pushkar4399/adservice:latest ."
                                 sh "docker push pushkar4399/adservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('cartservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/cartservice/src/') {
                                 sh "docker build -t pushkar4399/cartservice:latest ."
                                 sh "docker push pushkar4399/cartservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('checkoutservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/checkoutservice/') {
                                 sh "docker build -t pushkar4399/checkoutservice:latest ."
                                 sh "docker push pushkar4399/checkoutservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('currencyservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/currencyservice/') {
                                 sh "docker build -t pushkar4399/currencyservice:latest ."
                                 sh "docker push pushkar4399/currencyservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('emailservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/emailservice/') {
                                 sh "docker build -t pushkar4399/emailservice:latest ."
                                 sh "docker push pushkar4399/emailservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('frontend') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/frontend/') {
                                 sh "docker build -t pushkar4399/frontend:latest ."
                                 sh "docker push pushkar4399/frontend:latest"
                        }
                    }
                }
            }
        }
		
		stage('loadgenerator') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/loadgenerator/') {
                                 sh "docker build -t pushkar4399/loadgenerator:latest ."
                                 sh "docker push pushkar4399/loadgenerator:latest"
                        }
                    }
                }
            }
        }
		
		stage('paymentservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/paymentservice/') {
                                 sh "docker build -t pushkar4399/paymentservice:latest ."
                                 sh "docker push pushkar4399/paymentservice:latest"
                        }
                    }
                }
            }
        }
        
		stage('productcatalogservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/productcatalogservice/') {
                                 sh "docker build -t pushkar4399/productcatalogservice:latest ."
                                 sh "docker push pushkar4399/productcatalogservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('recommendationservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/recommendationservice/') {
                                 sh "docker build -t pushkar4399/recommendationservice:latest ."
                                 sh "docker push pushkar4399/recommendationservice:latest"
                        }
                    }
                }
            }
        }
		
		stage('shippingservice') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {
                          dir('/var/lib/jenkins/workspace/10-tier/src/shippingservice/') {
                                 sh "docker build -t pushkar4399/shippingservice:latest ."
                                 sh "docker push pushkar4399/shippingservice:latest"
                        }
                    }
                }
            }
        }
        
        stage('K8') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'my-eks2', contextName: '', credentialsId: '40662307-ca84-4893-ab4b-f6ffadfc3f8c', namespace: 'devops', restrictKubeConfigAccess: false, serverUrl: 'https://7DF03B658F34713AF60204C79AB4DF84.gr7.ap-south-1.eks.amazonaws.com') {
                       sh "kubectl apply -f deployment-service.yml"
					   sh "kubectl get pods -n devops"
					   sh "kubectl get svc -n devops"
}
            }
        }


    }
}

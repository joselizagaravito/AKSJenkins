pipeline{
    agent any
    environment{
        AZURE_CLIENT_ID = credentials("client_id")
        AZURE_CLIENT_SECRET = credentials("client_secret")
        AZURE_SUBSCRIPTION_ID = credentials("subscription_id")
        AZURE_TENANT_ID = credentials("tenant_id")
    }
    stages{
        stage('Login to Azure'){
            steps{
                sh '''
                az login --service-principal \
                -u $AZURE_CLIENT_ID \
                -p $AZURE_CLIENT_SECRET \
                --tenant $AZURE_TENANT_ID
                
                az account set -subscription $AZURE_SUBSCRIPTION_ID
                '''
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                withCredentials([file(credentialsId: 'gcloud-sa-02', variable: 'GCLOUD_CREDS')]) {
                  sh '''
                  PATH=/gcloud/google-cloud-sdk/bin:$PATH
                  gcloug verion
                  gcloud auth activate-service-account  --key-file=$GCLOUD_CREDS
                  gcloud compute zones list
                  '''                 
            }
        }
    }
}
}

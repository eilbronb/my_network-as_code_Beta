node {
   stage ('Checkout Repository') {
       // Get our repo cloned and ready for action
       deleteDir()
       checkout scm
   }
   
   stage ('Validate Configuration') {
       sh 'ansible-playbook generate_configurations.yaml --syntax-check'
   }

   stage ('Validate Configration') {
       sh 'ansible-playbook deploy_configuration.yaml --syntax-check'
   }

   stage ('Generate Render Configurations') {
       //Generate configuration
       sh 'ansible-playbook generate_configurations.yaml'
   }

   stage ('Deploy Router Configuration ') {
       //Do some kind of testing
       sh 'ansible-playbook deploy_configuration.yaml'
   }
   
   stage ('Verify Connectivity') {
       //Ping some IPs
       sh 'ansible-playbook verify-connectivity.yaml'
   }
   
   stage ('Promotye Configuration to Production') {
       //Push to Production
   }

}
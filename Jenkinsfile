pipeline {
    agent any

    stages {
        
         stage('Performance Test Execution') {
            steps {
                sh '/home/azureuser/apache-jmeter-5.4.1/bin/jmeter -n -q ${WORKSPACE}/config-qa.properties -t ${WORKSPACE}/APIPerformanceTesting.jmx -l ${WORKSPACE}/results/APIPerformaceTesting-${BUILD_TAG}.jtl'
            }
        }
        
         stage('Publish Test Result') {
            steps {
             perfReport 'results/APIPerformaceTesting-${BUILD_TAG}.jtl'
            }
        }
    }
}

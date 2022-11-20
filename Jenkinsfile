node {
    def app

    stage('Clone repository') {
      
        checkout scm
    }

    stage('test') {
        
        echo params.CHARTVER
    }

    stage('Update GIT') {
        
        sh "cat ./charts/library/Chart.yaml"
        sh "sed -i 'appVersion.*+appVersion: "${params.CHARTVER}"+g' Chart.yaml"
    /*    sh "cat ./charts/library/Chart.yaml"
        sh "git add ."
        sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.BUILD_NUMBER}'"
        sh "git push -u origin main" 
    */        
        
    }
}
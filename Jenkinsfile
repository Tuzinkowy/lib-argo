node {
    def app

    stage('Clone repository') {
      
        checkout scm
    }

    stage('test') {
        
        echo CHARTVER
    }

    stage('Update GIT') {
        withCredentials([usernamePassword(credentialsId: 'portfolio', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
        
            sh "cat ./charts/library/Chart.yaml"
            sh "sed -i 's/appVersion: .*/appVersion: ${CHARTVER}/g' ./charts/library/Chart.yaml"
            sh "cat ./charts/library/Chart.yaml"
            sh "git add ."
            sh "git commit -m 'Done by Jenkins Job changemanifest: ${env.BUILD_NUMBER}'"
            sh "git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com/${GIT_USERNAME}/lib-argo.git HEAD:main" 
        }    
    }
}
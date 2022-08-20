   def projectPath ="ConsoleDotnet.csproj"


pipeline {
    agent any
     environment {
        dotnet ='C:\\Program Files (x86)\\dotnet\\'
        }
   options {
        // This is required if you want to clean before build
        skipDefaultCheckout(true)
    }
    stages {
        
        stage('***Cloning Started****') {
            steps {
                dir ('bin') {
                     deleteDir()
                 }
                echo 'Downloading..'
                echo 'Pulling...' + env.BRANCH_NAME
                echo 'Downloading Done'
            }
        }
        stage('Restore packages'){
           steps{
               bat "dotnet restore ${projectPath}"
             }
          }
         stage('Clean packages'){
           steps{
              bat "dotnet clean "+projectPath
             }
          }
        stage('build packages'){
           steps{
              bat "dotnet build "+projectPath
             }
          }
       stage('build publish'){
           steps{
              bat "dotnet publish ${projectPath}  --configuration Release --output .\\bin\\publish"
             }
          }
        
        stage('***Configuration Started****') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('***Building**'){
            steps{
                echo 'Generating build exe'
            }    
        }
        
        stage('***Executing test cases**'){
            steps{
                echo "test cases done"
                
            }
        }
        
        stage('** Publising  to artifactory'){
            
            steps{
               script{
                    zip zipFile: 'build-app.zip', archive: false, dir: './bin//publish', overwrite: true
                      
               }
               echo "Build publish to artifcatory  ${WORKSPACE}\\build-app.zip"
            }
        }
        
        
        
        
    }
}

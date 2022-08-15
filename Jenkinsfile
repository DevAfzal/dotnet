pipeline {
    agent any
   def projectPath ='C:\\Users\\afzal\\.jenkins\\workspace\\DotNet Pipeline\\consoleApp.csproj'
     environment {
        dotnet ='C:\\Program Files (x86)\\dotnet\\'
        }

    stages {
        
        stage('***Cloning Started****') {
            steps {
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
          stage('build packages'){
           steps{
              bat "dotnet publish "+projectPath
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
                
                echo "Build publish to artifcatory"
            }
        }
        
        
        
        
    }
}

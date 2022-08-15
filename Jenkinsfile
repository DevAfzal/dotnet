pipeline {
    agent any
    
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
              bat "dotnet restore dotnet\\consoleApp.csproj"
             }
          }
         stage('Clean packages'){
           steps{
              bat "dotnet clean dotnet\\consoleApp.csproj"
             }
          }
        stage('build packages'){
           steps{
              bat "dotnet build dotnet\\consoleApp.csproj"
             }
          }
          stage('build packages'){
           steps{
              bat "dotnet publish dotnet\\consoleApp.csproj"
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

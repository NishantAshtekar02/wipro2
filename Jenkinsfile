pipeline{
  agent any{

    stages{
      stage('Clone repository'){
        steps{
          git 'https://github.com/NishantAshtekar02/apachewebsite'
        }
      }
    
      stage('Deployment'){
        steps{
          script{
            sh '''
            sudo rm -rf /var/www/html/*
            sudo cp -r * /var/www/html/
            sudo chown -R www-data:www-data /var
            sudo chmod -R 755 /var/www/html
            '''
          }
        }
      }

      stage('Restart apache'){
        step{
          srcipt{
            sh 'sudo systemctl restart apache2'
          }
        }
      }
    }
  }
}

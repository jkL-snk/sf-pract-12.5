pipeline {
  agent {
    docker {
      image 'arey/mysql-client'
    }

  }
  stages {
    stage('execute 1st sql') {
      agent {
        docker {
          image 'arey/mysql-client'
        }

      }
      steps {
        sh 'mysql --user rfamro --host mysql-rfam-public.ebi.ac.uk --port 4497 --database Rfam -e \'select * from fr.fram_acc limit 1;\''
      }
    }

  }
}
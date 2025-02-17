pipeline
{
  agent any
  stages
  {
    stage('Compile Stage')
    {
      steps
      {
        withMaven(maven: 'MAVEN_HOME')
        {
          sh 'mvn clean compile'
        }
      }      
    }
    stage('Testing Stage')
    {
      steps
      {
        withMaven(maven: 'MAVEN_HOME')
        {
          sh 'mvn test'
        }
      }
    }
    stage('Deploying Stage')
    {
      steps
      {
        withMaven(maven: 'MAVEN_HOME')
        {
          sh 'mvn install'
        }
      }
    }
  }
  post
  {
    always
    {
      echo 'always executed'
    }
    success
    {
      echo 'only executed when its success'
    }
    failure
    {
      echo 'only executed when its failure'
    }
    unstable
    {
      echo 'only executed when its unstable'
    }
  }
}

pipeline
{
    agent any
    stages {
        stage('scm checkout')
        {steps {git 'https://github.com/ayodejiogunkanmi/mavenproject.git'}}

        stage('code compile')
        {steps {sh 'mvn compile'}}

        stage('unit test')
        {steps {sh 'mvn test'}}
    }
}
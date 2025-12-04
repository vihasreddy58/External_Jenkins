pipeline{
agent any
stages{
stage('Checkout'){
steps{
 git branch:'master',url:'https://github.com/vihasreddy58/External_Jenkins'
}
}

 stage('Installing Application') {
    steps {
        sh '''
        python3 -m venv venv
        source venv/bin/activate
        pip install --upgrade pip
        pip install -r requirements.txt
        '''
    }
}


stage('Test Application'){
steps{
 sh 'pytest test_app.py>result.txt||true'
 sh 'cat result.txt'
}
}
stage('Build Application'){
steps{
 sh 'echo "Building Application"'
 sh 'python3 app.py'
}
}
}
}

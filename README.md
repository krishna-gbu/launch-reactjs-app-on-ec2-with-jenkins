# launch-reactjs-app-on-ec2-with-jenkins

## create ec2 instance of ubuntu(22 lts)
![image](https://user-images.githubusercontent.com/40553867/201734243-d31db011-6b19-4b92-8806-ae2b2da60768.png)

## connect ec2 instance with ssh 
![image](https://user-images.githubusercontent.com/40553867/201734496-37268a51-a051-4a22-8051-d01db4569a1e.png)

## update your apt(advance packing tool)
![image](https://user-images.githubusercontent.com/40553867/201735301-fb538566-19a8-43b1-b10e-a0095f832db7.png)

```
sudo apt update -y
```

## install nodejs (18)
```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```

![image](https://user-images.githubusercontent.com/40553867/201737047-bbe0c745-65f6-4456-b2d7-c005c513c054.png)
install yarn 

```
npm install --global yarn
```

![image](https://user-images.githubusercontent.com/40553867/201738302-b2a49140-a87b-4ca0-84c7-9c2e1717f4c8.png)

## install ngix

![image](https://user-images.githubusercontent.com/40553867/201739646-b503d439-f1e7-4fd3-8897-73dec08f5542.png)

![image](https://user-images.githubusercontent.com/40553867/201740854-e59ffbc9-ae8f-4a69-89ac-15ecf624d8d1.png)
## nginx index.html file location
![image](https://user-images.githubusercontent.com/40553867/201740993-8e4bd277-f76d-4cbd-a6c7-77453bd82174.png)

# now jenkins in picture

![image](https://user-images.githubusercontent.com/40553867/201829842-7daeb359-b25e-4361-b49c-c097ed129b36.png)

![image](https://user-images.githubusercontent.com/40553867/201829441-30098a81-fe3c-4a17-9368-695bd7211d89.png)

![image](https://user-images.githubusercontent.com/40553867/201829505-1ffa166e-bdba-4480-8ee4-ad4d2188a6e1.png)

## this is only testing purpose

![image](https://user-images.githubusercontent.com/40553867/201830391-01b015a1-89bc-49e0-97ac-56a5ec5f21a6.png)

## pipeline
```
pipeline {
    agent {label "ubuntu_slave"}

    stages {
        stage('git scm') {
            steps {
               git branch: 'main', url: 'https://github.com/krishna-gbu/launch-reactjs-app-on-ec2-with-jenkins.git'
            }
        }
         stage('deploy scm') {
            steps {
                sh 'yarn'
                sh 'yarn run build'
                sh 'sudo cp -r build/* /usr/share/nginx/html/'
                sh 'sudo systemctl restart nginx'
            }
        }
    }
}

```
![image](https://user-images.githubusercontent.com/40553867/201832196-d06a9c40-22ef-43d2-adea-59b567b5bf8b.png)

## port 80 allow from inbound firewall aws
![image](https://user-images.githubusercontent.com/40553867/201832532-afa45a0f-70ac-44e2-a955-b83e065e63ad.png)


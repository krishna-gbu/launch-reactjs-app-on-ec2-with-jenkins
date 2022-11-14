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


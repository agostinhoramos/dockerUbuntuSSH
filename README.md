# Ubuntu SSH using Docker

This is a small demo of remote SSH connection using docker.
I'm using the Ubuntu distribution, but any other distribution will also work. :)

## Please run the following steps


1 - Build Dockerfile
```
docker build --tag=ubuntu_ssh .
```

2 - Run docker image
```
docker run -d --name ubuntuSSH -p 2022:22 ubuntu_ssh
```

3 - Check if port 2022 exist
```
sudo netstat -ntlp | grep LISTEN
```

5 - Start SSH connection
```
ssh -p 2022 user@127.0.0.1
```


4 - Start SFTP connection
```
sftp -oPort=2022 user@127.0.0.1
```
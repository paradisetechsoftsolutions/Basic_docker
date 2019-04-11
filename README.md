# Basic_docker
## What is docker 
<ol>
<li>
<strong>Docker</strong> is a computer program which used to provide a running environment to run all kinds of application those are in docker hub, or we create in docker.</br>
It creates an image of your application and stores all requirements of files into the container. Whenever we want to run docker application in any system, we have to run a single file without providing any other requirements.</li></br>
<li><strong>Docker</strong> is easy to use in <strong>Ubuntu</strong>. It also supports <strong>Window</strong> and <strong>Mac</strong> operating system.</br>
For the <strong>window</strong>, it runs in <strong>Windows10/enterprise</strong> only. To use in <strong>Windows7/8/8.1</strong> or <strong>Windows10 home</strong> should use docker toolbox.</li></br>
<li>There are two kind of docker software for programmers.</li>
<ol>
<li><strong>Docker CE</strong> :- <strong>Free community edition</strong> :- This is an open source software. </li>
<li><strong>Docker EE</strong> :- <strong>Docker Enterprise Edition</strong> :- This is a paid software design for enterprise development and IT teams who build, ship, and run business-critical applications in production. </li></br>
</ol>
</ol>

## Steps to install docker
<li><strong>Steps to download docker in ubuntu.</strong></li>
<ol>
<li>Open terminal and follow these command to install docker.</li></br>
<ol>
<li>Just type 'docker' and check if docker is  in your system or not.</br> 
    <strong>$ docker</strong></li> </br>
<li>To check the version of operating system.</br>
    <strong>$ lsb_release -a</strong></li></br>  
    
![lsb](https://user-images.githubusercontent.com/47202519/55958568-9bc0fd00-5c86-11e9-8707-25daa20fded7.png)
 
<li>Update the apt package index.</br>
    <strong>$ sudo apt-get update</strong></li></br>
<li>If require then install. </br>
    <strong>$ sudo apt-get install </strong></li></br>
<li>If docker is not in your system then install it. </br>
    <strong>$ sudo apt-get install docker.io</strong></li></br>
<li>Now check the staus of docker.</br>
    <strong>$ sudo systemctl status docker</strong> </li></br>
 </ol> 
 </ol>
 
## Steps to add user in docker
<ol>
<li><strong>Why sudo :-</strong> </br>
We have to use <strong>'sudo'</strong> command to run docker commands because docker container run  <strong>user 'root'</strong> we have to join the docker group, when your system join docker group after that we can  run docker command without <strong>sudo</strong>.</li></br>
<li><strong>'USER'</strong> is your system name, command to add user. </br>
<strong>$user</strong> will pick system user</li>
  <ol>
      <li><strong>$ sudo groupadd docker</strong></li>
      <li><strong>$ sudo gpasswd -a $USER </strong></li>
      <li><strong>$ newgrp docker</strong></li>
  </ol></br>
    
<li>Second way to add user in docker group.</li>
  <ol>
      <li><strong>$ sudo groupadd docker</strong></li>
      <li><strong>$ sudo usermod -aG docker $USER </strong></li>
  </ol></br>
        
<li>After adding a <strong>'USER'</strong> into the docker group, we have to <strong>shut down</strong> or <strong>restart</strong> our system and then we can run docker commands without <strong>'sudo'</strong> command.</li></br>  

<li>Command to uninstall docker.</li>
   <strong>$ sudo apt-get remove docker docker-engine docker.io containerd runc</strong></br>
</li>
</ol>


### Docker commands
<ol>
<li>To check Docker version </br>
<strong>$ docker --version</strong></li></br>

<li>To check Docker and containers info</br>
<strong>$ docker info</strong></li></br>

<li>Find out which users are in the docker group and allowed to start docker containers.</li>
 <ol>
    <li><strong>$ getent group sudo</strong></li>
    <li><strong>$ getent group docker</strong></li>
 </ol></br>

<li><strong>'pull'</strong> command fetch the <strong>'name_of_images'</strong> image from the <strong>'Docker registry'</strong> and saves it to our system.</br>
<strong>$ docker pull busybox</strong> (busybox is name of image)</li></br>

<li>You can use the <strong>'docker images'</strong> command to see a list of all images on your system.</br>
<strong>$ docker images</strong></li></br>

<li>Now run a Docker container based on this image. When you call run, the Docker client finds the image (busybox in this case), loads up the container and then runs a command in that container.</br> 
<strong>$ docker run busybox</strong></li></br>

<li>Now Docker client  ran the 'echo' command in our busybox container and then exited it.</br>
<strong>$docker run busybox echo "hello from busybox"</strong></li></br>

<li>Command to shows you all containers that are currently running.</br>
<strong>$ docker ps</strong></li></br>

<li>list of all containers that we ran. Do notice that the <strong>STATUS</strong> column shows that these containers exited a few minutes ago.</br>
<strong>$ docker ps -a</strong></li></br>

<li>To start Container<br>
<strong>$ docker start (container id)</strong></li></br>

<li>To login in Container<br>
<strong>$ docker attach (container id)</strong></li></br>

<li>To stop container</br>
<strong>$ docker stop (container id)</strong></li></br>
</ol>

### Remove images and containers
<ol>
<li>docker rm command. Just copy the container IDs.</br>
 <strong>$ docker rm ed1e38efb51a (container_id)</strong></li></br>

<li>Command to deletes all containers that have a status of exited.</br>
-q flag, only returns the numeric IDs and -f filters output based on conditions provided.</br>
<strong>$ docker rm $(docker ps -a -q -f status=exited)</strong></li></br>

<li>Command to delete all container.</br>
<strong>$ docker container prune</strong></li></br>

<li>Command to delete all images.</br>
<strong>$ docker images prune -a</strong></li></br>

<li>Command to delete all container and images. </br>
<strong>$ docker system prune -a</strong></li></br>
</ol>

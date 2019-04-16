# Basic_docker
## What is docker 
<ol>
<li>
<strong>Docker</strong> is a computer program which is used to provide a running environment to run all kinds of application which are in docker hub, or create in docker.</br>
It creates an image of your application and stores all requirements of files into the container. Whenever we want to run docker application in any system, we have to run a single file without providing any other requirements.</li></br>
<li><strong>Docker</strong> is easy to use in <strong>Ubuntu</strong>. It also supports <strong>Window</strong> and <strong>Mac</strong> operating system.</br>
For the <strong>window</strong>, it runs in <strong>Windows10/enterprise</strong> only. To use in <strong>Windows7/8/8.1</strong> or <strong>Windows10 home</strong> should use docker toolbox.</li></br>
<li>There are two kind of docker software for programmers.</li>
<ol>
<li><strong>Docker CE</strong> :- <strong>Free community edition</strong> :- This is an open source software. </li>
<li><strong>Docker EE</strong> :- <strong>Docker Enterprise Edition</strong> :- This is a paid software design for enterprise development and IT teams who build, ship, and run business-critical applications in production. </li></br>
</ol>
</ol>

## Requirements :-
<ol>
<li>Operating system (ubuntu)</li>
<li>Docker</li>
</ol>

## Steps to install docker
<li><strong>Steps to download docker in ubuntu.</strong></li>
<ol>
<li>Open terminal and follow these command to install docker.</li></br>
<ol>
<li>Just type 'docker' and check if docker is  in your system or not.</br> 
    <strong>$ docker</strong></li> </br>
<li>To check the version of operating system.</br>
   <li> <strong>$ lsb_release -a</strong></li></br> 
   
   ![lsb](https://user-images.githubusercontent.com/47202519/56012407-fd767b00-5d09-11e9-89aa-275c02857584.png)

 
<li>update the apt package index.</br>
    <strong>$ sudo apt-get update</strong></li></br>
<li>If require then install. </br>
    <strong>$ sudo apt-get install </strong></li></br>
<li>If docker is not in your system then install it. </br>
    <strong>$ sudo apt-get install docker.io</strong></li></br>
<li>Now check the staus of docker.</br>
    <strong>$ sudo systemctl status docker</strong> </li></br>  
    
   ![status](https://user-images.githubusercontent.com/47202519/56012484-58a86d80-5d0a-11e9-914b-6b65463ee5e8.png)

 </ol> 
 </ol>
 
## Steps to add user in docker
<ol>
<li><strong>Why sudo :-</strong> </br>
We have to use <strong>'sudo'</strong> command to run docker commands because docker container run  <strong>user 'root'</strong> we have to join the docker group, when your system join docker group after that one can  run docker command without <strong>sudo</strong>.</li></br>
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
        
<li>After adding a <Operating system (ubuntu)strong>'USER'</strong> into the docker group, we have to <strong>shut down</strong> or <strong>restart</strong> our system and then we can run docker commands without <strong>'sudo'</strong> command.</li></br>  

<li>Command to uninstall docker.</li>
   <strong>$ sudo apt-get remove docker docker-engine docker.io containerd runc</strong></br>
</li>
</ol>


### Docker commands
<ol>
<li>To check Docker version </br>
<strong>$ docker --version</strong></li></br>  

![version](https://user-images.githubusercontent.com/47202519/56012976-6c54d380-5d0c-11e9-84c2-31afabecfa5f.png)

<li>To check Docker and containers info</br>
<strong>$ docker info</strong></li></br>

<li>Find out which users are in the docker group and allowed to start docker containers.</li>
 <ol>
    <li><strong>$ getent group sudo</strong></li>  
    
  ![sudo](https://user-images.githubusercontent.com/47202519/56012925-239d1a80-5d0c-11e9-99bc-97750baaae91.png)  
    
   <li><strong>$ getent group docker</strong></li>  
   
   ![docker](https://user-images.githubusercontent.com/47202519/56012934-2dbf1900-5d0c-11e9-8fca-840e6a032dcb.png)
   
 </ol></br>

<li><strong>'pull'</strong> command fetch the <strong>'name_of_images'</strong> image from the <strong>'Docker registry'</strong> and saves it to our system.</br>
<strong>$ docker pull busybox</strong> (busybox is name of image)</li></br> 

![busybox](https://user-images.githubusercontent.com/47202519/56012945-3c0d3500-5d0c-11e9-8f78-c6314b28effa.png)


<li>You can use the <strong>'docker images'</strong> command to see a list of all images on your system.</br>
<strong>$ docker images</strong></li></br>  

![d_img](https://user-images.githubusercontent.com/47202519/56013130-f9982800-5d0c-11e9-85a2-5ac28156deb0.png)

<li>Now run a Docker container based on this image. When you call run, the Docker client finds the image (busybox in this case), loads up the container and then runs a command in that container.</br> 
<strong>$ docker run busybox</strong></li></br>

<li>Now Docker client  ran the 'echo' command in our busybox container and then exited it.</br>
<strong>$docker run busybox echo "hello from busybox"</strong></li></br>  

![echo](https://user-images.githubusercontent.com/47202519/56013136-03219000-5d0d-11e9-9c96-1077fc214120.png)

<li>Command to shows you all containers that are currently running.</br>
<strong>$ docker ps</strong></li></br>  

![ps](https://user-images.githubusercontent.com/47202519/56013147-0ae13480-5d0d-11e9-83a4-33e6856239a7.png)

<li>List of all containers that one can run. Do notice that the <strong>STATUS</strong> column shows that these containers exited a few minutes ago.</br>
<strong>$ docker ps -a</strong></li>
CONTAINER ID – Unique ID given to all the containers.</br>
IMAGE – Base image from which the container has been started.</br>
COMMAND – Command which was used when the container was started </br>
CREATED – Time at which the container was created.</br>
STATUS – The current status of the container (Up or Exited).</br>
PORTS – Port numbers if any, forwarded to the docker host for communicating with the external world.</br>
NAMES –  You can specify your own name.</br>  

![ps-a](https://user-images.githubusercontent.com/47202519/56013152-0ddc2500-5d0d-11e9-969c-07e0ba4c9bcf.png)

<li>To start Container<br>
<strong>$ docker start (container id)</strong></li></br> 

![start](https://user-images.githubusercontent.com/47202519/56013161-19c7e700-5d0d-11e9-8325-d615d50f8d20.png)

<li>To login in Container<br>
<strong>$ docker attach (container id)</strong></li></br>

<li>To stop container</br>
<strong>$ docker stop (container id)</strong></li></br>

![stop](https://user-images.githubusercontent.com/47202519/56013171-251b1280-5d0d-11e9-9c0a-d8d20e147ce0.png)

</ol>
  

### Remove images and containers
<ol>
<li>Docker rm command. Just copy the container IDs.</br>
 <strong>$ docker rm 419600f601f9 (container_id)</strong></li></br>  
 
 ![rm](https://user-images.githubusercontent.com/47202519/56014043-3cf49580-5d11-11e9-9782-21aaf0961b01.png)

<li>Command to deletes all containers that have a status of exited.</br>
-q flag, only returns the numeric IDs and -f filters output based on conditions provided.</br>
<strong>$ docker rm $(docker ps -a -q -f status=exited)</strong></li></br>  

![exit](https://user-images.githubusercontent.com/47202519/56014051-454cd080-5d11-11e9-9b63-dc2f2ba97381.png)

<li>Command to delete all container.</br>
<strong>$ docker container prune</strong></li></br>  

![c_purne](https://user-images.githubusercontent.com/47202519/56014072-5695dd00-5d11-11e9-9439-4b44f3c40306.png)

<li>Command to delete all images.</li>
<strong>$ docker images prune -a</strong></br> 

![img_prune3](https://user-images.githubusercontent.com/47202519/56014105-7927f600-5d11-11e9-97fb-bc0cd86a0a18.png)

<strong>$ docker images -q</strong></br>  

![img_prune2](https://user-images.githubusercontent.com/47202519/56014120-7e854080-5d11-11e9-9f38-8a0184d8de28.png)

<strong>$ docker images prune </strong></br>  

![img_prune](https://user-images.githubusercontent.com/47202519/56014138-9230a700-5d11-11e9-8a1f-fac8eb0eb692.png)

<strong>$ docker rmi image_id image_id...... </strong></li></br>  

![delt_img](https://user-images.githubusercontent.com/47202519/56014153-9bba0f00-5d11-11e9-804f-97509608c271.png)</br>


<li>Command to delete all container and images. </br>

<strong>$ docker system prune -a</strong></li></br>  

![system_prune](https://user-images.githubusercontent.com/47202519/56014191-cd32da80-5d11-11e9-97cd-603f5c24f2d1.png)


</ol>

## In next README file we will discuss about docker database(MYSQL & phpmyadmin)</br>
https://github.com/amit-kumar001/Docker_connection_with_MYSQL

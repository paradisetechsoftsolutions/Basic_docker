# Basic_docker
## What is docker 
<ol>
<li>
<strong>Docker</strong> is a computer program which used to provide a running environment to run all kind of application those are in docker hub, or we create in docker.</br>
It creates an image of your application in and stores all requirement of files into the container. Whenever we want to run docker application in any system, we have to run a single file without providing any other requirement.</li>
<li><strong>Docker</strong> is easy to use in <strong>Ubuntu</strong>. It also supports <strong>Window</strong> and <strong>Mac</strong> operating system.</br>
For the <strong>window</strong>, it runs in <strong>Windows10/enterprise</strong> only. To use in <strong>Windows7/8/8.1</strong> or <strong>Windows10 home</strong> should use docker toolbox.</li>
<li>There are two kind of docker software for programmers</li>
<ol>
<li><strong>Docker CE</strong> :- <strong>Free community edition</strong> :- This is a open source software </li>
<li><strong>Docker EE</strong> :- <strong>Docker Enterprise Edition</strong> :- This is a paid software design for enterprise development and IT teams who build, ship, and run business-critical applications in production </li>
</ol>
</ol>

## Steps to install docker
<li><strong>Steps to download docker in ubuntu</strong></li>
<ol>
<li>Open terminal and follow these command to install docker.</li>
<ol>
<li>Just type 'docker' and check if docker is  in your system or not</br> 
    <strong>$ docker</strong></li> 
<li>To check the version of operating system</br>
    <strong>$ lsb_release -a</strong> </li>
<li>Update the apt package index.</br>
    <strong>$ sudo apt-get update</strong></li>
<li>If require then install </br>
    <strong>$ sudo apt-get install </strong></li>
<li>If docker is not in your system then install it </br>
    <strong>$ sudo apt-get install docker.io</strong></li>
<li>Now check the staus of docker </br>
    <strong>$ sudo systemctl status docker</strong> </li>
 </ol> 
 </ol>
 
## Steps to add user in docker
<ol>
<li><strong>Why sudo :-</strong> </br>
We have to use <strong>'sudo'</strong> command to run docker commands because docker container run  <strong>user 'root'</strong> we have to join the docker group, when your system join docker group after that we can  run docker command without <strong>sudo</strong></li>
<li><strong>'USER'</strong> is your system name, command to add user </br>
  <ol>
      <li><strong>$ sudo groupadd docker</strong></li>
      <li><strong>$ sudo gpasswd -a $USER name_of_your_system</strong></li>
      <li><strong>$ newgrp docker</strong></li>
  </ol>
     now we can run docker commands without 'sudo'</li>
<li>Second way to add user in docker group</li>
  <ol>
      <li><strong>$ sudo groupadd docker</strong></li>
      <li><strong>$ sudo usermod -aG paradise $USER name_of_your_system</strong></li>
  </ol>
     now we can run docker commands without <strong>'sudo'</strong></li>
     
<li>Add a <strong>'USER'</strong> into the docker group after that we have to <strong>shut down</strong> or <strong>restart</strong> our system and then we can run docker commands without <strong>'sudo'</strong> command</li>   

<li>Command to uninstall docker</li></br> 
   $ sudo apt-get remove docker docker-engine docker.io containerd runc
</li>
</ol>


## Docker commands
<li>find out which users are in the docker group and allowed to start docker containers</li>
 <ol><li>getent group sudo</li>
     <li>getent group docker</li></ol>

<li>'pull' command fetches the 'name_of_images' image from the 'Docker registry' and saves it to our system.
 <li>docker pull busybox (busybox is name of image)</li></li>

<li>You can use the 'docker images' command to see a list of all images on your system.</li>
<li>docker images</li></li>


<li>Now run a Docker container based on this image. When you call run, the Docker client finds the image (busybox in this case), loads up the container and then runs a command in that container. 
<li>docker run busybox</li></li>

<li>In this case, the Docker client  ran the 'echo' command in our busybox container and then exited it. If you've noticed, all of that happened pretty quickly.
<li>docker run busybox echo "hello from busybox"</li></li>

<li>Command to shows you all containers that are currently running.
<li>docker ps</li></li>

<li>list of all containers that we ran. Do notice that the STATUS column shows that these containers exited a few minutes ago.
<li>docker ps -a</li></li>
</ol>

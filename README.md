<h1>Shoutcast Radio Media Streaming Server on Docker</h1>

DOCKERHUB URL: https://hub.docker.com/r/murderousone/shoutcast

</hr>
</h2>IMAGE WILL CONTAIN REALLY SIMPLE BASH SCRIPTS TO MAKE LIFE EASIER. NOTHING CODE SAVY.</h2>
<p>THIS DOCKER IMAGE WILL WORK WITH 64 Bit Systems.</br>
<b>DOCKER IMAGE MAY NOT WORK WITH  32bit Systems.</b></br>
<p>Image can be attached too and is fully customizable.</p>
<p>Image has simple pre-installed bash scripts to make running the server easier.</p>

<h1>Shoutcast Radio Media Streaming Server</h1>
<h2><p>Based on Ubuntu Server Latest 64 Bit </p></h2>

</br>
<h3>UPDATES FOR UBUNTU SERVER LATEST</h3>
* EASY SCRIPT FOR START, EDITING THE CONFIG</br>
* EASY SHELL EXACUTABLE SCRIPTS FOR EDITING, START, AND EASIER MANAGING</br>
* ALL UBUNTU PACKAGES UPDATED</br>
</hr>
<p>
	<span style="color:#3498db;"><strong>ENJOY!&nbsp;</strong></span>
</p>

<p>Docker image is a ubuntu x64 or Debian latest Shoutcast Radio Media Streaming Server base os which contains all the configuration created for setting up a radio streaming server</p>
<p>The docker image is also unlocked and contains pre-made bash scripts to run your streaming server even easier than our manual setup.</p>
<p>Docker also allows better performance and less resources to your computer / server.</p>

<h2> Install Docker</h2>

```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

FOR OTHER NON-LINUX OS's
<a href="https://docs.docker.com/get-docker/" target="_blank">GET DOCKER</a>

<h2>RUN THE DOCKER CONTAINER WITH DOCKER COMPOSE</h2>

<h3>Install Docker Compose on Linux</h3>

```
sudo curl -L "https://github.com/docker/compose/releases/download/v2.15.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
<p>To install Docker Compose on other non-Linux OS's <a href="https://docs.docker.com/compose/install/" target="_blank">Click here</a></p>


<h2>Downloading and Creating your container Using docker-compose (Ubuntu Image)</h2>

<h3>Create a new Directory</h3>

```
mkdir shoutcast
```

<h2>Create a Docker Compose file inside your new directory:</h2>
<p>(example: docker-compose.yml)</p>
​
<h2>Change Directory</h2>

```
cd shoutcast
```
​
<h3>Create the docker compose file:</h3>

```
nano docker-compose.yml
```

<p>add the code below for ubuntu and save</p>

```
version: "3"
services:
  shoutcast-radio-streaming-server:
    image: murderousone/shoutcast:ubuntu-latest
    volumes:
      - shoutcast:/shoutcast/examples/
    container_name: shoutcast-radio-server
    restart: unless-stopped
    stdin_open: true
    tty: true
    ports:
      - "8000:8000"
      - "8001:8001"
      - "80:80"
      - "443:443"

volumes:
  shoutcast:

```

<h2>To update the container with Docker Compose:</h2>
<p># Pull the latest updated image </p>

```
docker-compose pull
```

<p># To Create, Start, the container</p>


```
docker-compose up -d
```

<p>delete the container </p>

```
docker-compose down
```

<p>Above docker command will pull the image, create, run and start the Docker Container / Shoutcast Radio Streaming Server already configured with ports opened.<p></br>
<p>Volume must be deleted manually to go back to default config on you edit and add your credentials.</p>

<h2> List and Delete a Volume </h2>

<h3>List Docker Volumes</h3>

```
docker volume ls
```

<h2>Delete Docker Volumes</h2>

```
docker volume rm volume_name
```

<h2>Attach to the Running Shoutcast Radio Streaming Server Docker Container</h2>

```
docker attach shoutcast-radio-server
```

<h2>To Update the server packages on the Shoutcast Radio Streaming Server Docker Container</h2>

```
./update
```

<h2>Edit and Add your SHOUTCAST CREDENTIALS</h2>

```
./edit-shoutcast
```

<h2>START THE Shoutcast Radio Streaming Server</h2>

```
./start-shoutcast
```

<h2>EXIT THE CONTAINER WHILE LEAVING IT RUNNING</h2>

```
HOLD: CRTL + p + q 
```

<p>Your docker Shoutcast Radio Streaming Server is now started and running in the background...</p>
<p>You can now connect to it, using your preferred streaming radio software. (Mixx, , Virtual DJ, Winamp, etc)</p>


ENJOY! 

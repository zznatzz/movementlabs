# movementlabs

# 1. Hardware Requirements:
# >= 8 Cores CPU (or vCPU)
# >= 16 GB RAM
# >= 128 GB Disk


# 2. Environment Deployment

  # 1 Install the docker

  apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin 
  docker-compose-plugin && systemctl start docker

or

# https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04


 # 2 Pull the docker

  docker pull mvlbs/m1-testnet:latest

#  3 Run and enter the container

  docker run -itd -v "$(pwd):/workspace" mvlbs/m1-testnet /bin/bash

# 3. Run the node in a new windows or screen and obtain node ID in a new windows or screen 
 # Start the node 
 
  sudo apt install screen
  
  screen -S move
  
  movement ctl start m1 testnet
  
  # do a ctl + a + d to get out of screen

  sudo ufw allow 9650/tcp
  
  docker ps # get the container id 
  
  docker exec -it CONTAINER_ID bash



  curl -X POST --data '{
  "jsonrpc":"2.0",
  "id" :1,
  "method" :"info.getNodeID"
  }' -H 'content-type:application/json;' 127.0.0.1:9650/ext/info


# You will then receive the node’s ID, publicKey and proofOfPossession (private key). Please keep them secure and do not disclose them.

# 4. Tutorial for Applying for an Official License
# To apply for an official license, you must submit a form to Movement Labs. Your role will be granted in its official Discord.

# Application address:

https://form.asana.com/?k=K9Xj5wZLNu7u6EfxD5KTEg&d=1204965688263

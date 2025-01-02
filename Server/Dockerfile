# we will start by specifying the base image's operating system which we kept as ubuntu
FROM ubuntu
# then for this base image we need to install node on it 
RUN apt-get update
RUN apt-get install -y curl
RUN curl -sl https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get upgrade -y    
RUN apt-get install -y nodejs

# we copy of the necessary files to be kept in the docker image
# copy from source to destination
COPY package.json package.json
COPY package-lock.json package-lock.json
COPY index.js index.js

# we specify the run command 
RUN npm install 

# we specify the entry point
ENTRYPOINT [ "node" , "index.js" ]



# now to create the image we run the command -> docker build -t aditya-nodejs-app

# now if you check you'll see the image in the docker desktop but this image is still not on docker.io but on our local machine 

# to test the image run -> docker run -it aditya-nodejs-app it will show the server running statement but as we still haven't exposed 
# the port we can't open it on our own port so for it -> 
# Specify a base image
FROM node:alpine

# This line is because create-react-app open bug with Docker
ENV CI=true

# This creates the folder "app" inside "usr" inside the container
WORKDIR /usr/app

# Copying the package.json on the container before installing
COPY ./package.json ./
# Install some dependencies
RUN npm install
# Once packages are installed, we copy the whole rest of the app to use our cache just for code changes
COPY ./ ./

# Tell the image what to do when it starts as a container
CMD [ "npm", "start" ]

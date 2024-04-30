# Specifies the base image we're extending
FROM node:9

# Specify the "working directory" for the rest of the Dockerfile
WORKDIR /src

# Install packages using NPM 5 (bundled with the node:9 image)
COPY node-docker-demo/package.json /src/package.json
COPY node-docker-demo/package-lock.json /src/package-lock.json
RUN npm install --silent

# Add application code
COPY node-docker-demo/app /src/app
COPY node-docker-demo/bin /src/bin
COPY node-docker-demo/public /src/public

# Add the nodemon configuration file
COPY node-docker-demo/nodemon.json /src/nodemon.json

# Set environment to "development" by default
ENV NODE_ENV development

# Allows port 3000 to be publicly available
EXPOSE 3000

# The command uses nodemon to run the application
CMD ["node", "node_modules/.bin/nodemon", "-L", "bin/www"]

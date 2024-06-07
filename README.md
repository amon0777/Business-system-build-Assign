# Codin 1 Web Application

This project sets up a development environment for a simple React application that displays a `<h1>` tag with the text "Codin 1" using Docker.

## Prerequisites

- Docker installed on your machine

## Getting Started

Follow these steps to get the application running on `localhost:7775`.

### Step 1: Create React App

First, create a React application if you haven't already:

```sh
npx create-react-app codin-1
cd codin-1
Step 2: Modify the App Component
Open src/App.js and replace its content with the following code to display the text "Codin 1":


import React from 'react';

function App() {
  return (
    <div className="App">
      <h1>Codin 1</h1>
    </div>
  );
}

export default App;
Step 3: Create the Dockerfile
In the root directory of your React project (codin-1), create a Dockerfile with the following content. This file will set up the Docker environment for your application:

# Use the official Node.js image as the base image
FROM node:16-alpine

# Set the working directory in the container
WORKDIR /bhatti_amon_site

# Copy the package.json and package-lock.json files to the working directory
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 7775
EXPOSE 7775

# Start the React application
CMD ["npm", "start"]


Step 4: Build the Docker Image
Open a terminal and navigate to the root directory of your project (codin-1). Run the following command to build the Docker image:

docker build -t bhatti_amon_coding_assignment11 .
Step 5: Run the Docker Container
After building the image, start the Docker container with the following command:

docker run -p 7775:3000 --name bhatti_amon_coding_assignment11 bhatti_amon_coding_assignment11
This command maps port 3000 in the container to port 7775 on your local machine, allowing you to access the application at http://localhost:7775.

Step 6: Verify the Application
Open your web browser and navigate to http://localhost:7775. You should see the webpage displaying the text "Codin 1".
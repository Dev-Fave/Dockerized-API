
Dockerized API + CI/CD

 Project Overview

This project guides you through creating a simple API, running it inside Docker, pushing your code to GitHub, and setting up CI/CD.
By the end of this walkthrough, you will have:
A working API inside a Docker container
Your project version-controlled on GitHub
Automated CI/CD pipelines running on code changes

 What You Will Learn
How to Dockerize an API
How to build and run Docker containers
How to push code to GitHub
How to automate CI/CD for your API

step-by-Step Guide

Step 0: Open Your Tools

Make sure everything is ready before you start:
Open PowerShell

Open VS Code

Open Docker Desktop

Wait until it says: Docker is running


Step 1: Navigate to Your API Project

Open PowerShell and go to your project folder:

cd path\to\your\project

Step 2:

Create Dockerfile

Create a Dockerfile in your project root:

# Use Node.js as the base image

FROM node:18

# Set working directory

WORKDIR /app

# Copy package.json and install dependencies

COPY package*.json ./

RUN npm install

# Copy project files

COPY . .

# Expose the API port

EXPOSE 3000

# Start the API

CMD ["npm", "start"]

Step 3: Build Docker Image
docker build -t simple-api .

Step 4: Run Docker Container

docker run -p 3000:3000 simple-api

Check your API in the browser at http://localhost:3000.
Step 5: Push to GitHub

git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main

Step  6:Setup CI/CD (GitHub Actions)
Create .github/workflows/ci-cd.yml

Add workflow to build Docker and run tests automatically on push

Notes
This guide assumes a Node.js API, but the steps can be adapted for other languages.

Docker must be running before building or running containers.

CI/CD workflows depend on your GitHub repository setup.



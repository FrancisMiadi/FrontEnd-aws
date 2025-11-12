#!/bin/bash

echo "Starting frontend setup..."

cd client

# Step 1: Install dependencies

echo "Installing dependencies..."
npm install

# Step 2: Create .env file from example

if [ -f ".env.example" ]; then
echo "Creating .env file..."
cp .env.example .env
echo ".env file created. Please update the following before running in production:"
echo "- # Replace the placeholder strings with your actual API key
(The API key will be provided on WhatsApp)"
else
echo ".env.example not found. Please make sure it exists in the project root."
exit 1
fi

# Step 3: Start the frontend server

echo "Starting the frontend server..."
npm start

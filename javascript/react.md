# React

### Create React App

```
# Step 1 Create boilerplate react app and use npm instead of yarn:
# Command: npx create-react-app <app_name> --use-npm
npx create-react-app test-app --use-npm

# Step 2:
cd test-app

#Step 3 - available commands:
# Start the development server.
npm start

# Bundles the app into static files for production.
npm run build

# Starts the test runner.
npm test

# Removes this tool and copies build dependencies, configuration files
# and scripts into the app directory. If you do this, you can't go back.
npm run eject


```

### Build

```
npm run build
```

### Run production build on local server

```
// Setup server globally on local environment
sudo npm i -g serve

// Start the server and provide the 
serve -s build -p 8000

// As a result you will get the server address:
// - Local:            http://localhost:8000      │
// - On Your Network:  http://192.168.0.22:8000
```

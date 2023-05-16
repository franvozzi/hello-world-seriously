
# Building a Hello World Electron App
This tutorial will guide you through the process of creating a simple "Hello, World!" Electron application and packaging it as an executable.

## Prerequisites
Make sure you have the following software installed on your computer:

Node.js and npm (Node Package Manager). You can download them from the official Node.js website: https://nodejs.org/

## Step-by-Step Instructions
### Step 1: Set Up the Project
Create a new project directory for your Electron application.

Initialize a new npm project by running the following command:

shell
Copy code
npm init -y
Step 2: Install Electron
In the terminal, install Electron as a development dependency by running the following command:

shell
Copy code
npm install electron --save-dev
### Step 3: Create the Main Script
Create a new file called main.js in your project directory.

Open main.js in a text editor and add the following code:

```
const { app, BrowserWindow } = require('electron');

function createWindow() {
  const win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true
    }
  });

  win.loadFile('index.html');
}

app.whenReady().then(createWindow);
```
### Step 4: Create the HTML File
Create a new file called index.html in your project directory.

Open index.html in a text editor and add the following code:
```
<!DOCTYPE html>
<html>
<head>
  <title>Hello, World!</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <script src="renderer.js"></script>
</body>
</html>
```

### Step 5: Create the Renderer Script
Create a new file called renderer.js in your project directory.

Open renderer.js in a text editor and add the following code:

```
console.log("Hello from renderer script!");
```

Step 6: Update package.json
Open your package.json file and modify the "scripts" section to include the following:

```
"scripts": {
  "start": "electron ."
}
```

### Step 7: Run the Application
To run your Electron application, use the following command:

```
npm start
```

### Step 8: Build an Executable
To build an executable file for your Electron application, we'll use electron-builder. Follow these steps:

Install electron-builder as a dev dependency by running the following command:

```
npm install electron-builder --save-dev
```

Update your package.json file with the necessary configuration for electron-builder.

Open your terminal or command prompt and run one of the following commands based on your target platform:

For Windows:
```
npm run build:win
```

For macOS:

```
npm run build:mac
```


## Authors

- [@franvozzi](https://www.github.com/franvozzi)


## License

[MIT](https://choosealicense.com/licenses/mit/)







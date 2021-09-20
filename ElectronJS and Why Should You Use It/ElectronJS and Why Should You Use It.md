# ElectronJS and Why Should You Use It?
Let’s take a step back before we speak about ElectronJs and see how Desktop applications are made. We will also analyze the issues with the current way of developing the Desktop applications

### App Development on different platforms

#### Windows:
Most people use C++, C# (C Sharp), VB (Visual Basic) for development. This may include using/reusing some open source .NET libraries to make applications across all the windows ecosystems like Windows store, windows phone, windows desktop applications.

#### MacOS:
Mostly Standard C, C++, Objective-C and Swift used for development. There is a lot you need to learn about the technologies & frameworks in order to develop apps on macOS. 
'Cocoa' for UI, 'Media' for Media operations, Photo & Video editing.

#### Linux: 
Linux is one of the most popular OS for developers, so we want our products to reach Linux users. Linux typically uses Python or other libraries for the User Interface of the application. For Linux, if you need services like 3D and 2D rendering, you will need OpenGL. Linux Kernel exposes the low-level functionalities.

### What is with Web Technologies?
Web development is one of the hottest topics out there and there is no surprise that the population of web developers is rather high. There are also a lot of web developers available who can design and create apps with amazing UI/UX. They are easy to find because these technologies are standard and are being used by top companies in the world for their production projects. There are innumerable frameworks out there helping other teams, backed by tech giants in the industry.

If we just depend on conventional methods, we need a lot of capital and time to achieve this. Instead, if we use web technologies, we can reuse a lot of open source frameworks and solve issues efficiently.

If you want your application to be available for all the platforms we talked about, you need to deploy your app using different technologies. This is very manual and time-consuming. 
This is where ElectronJs comes into the picture.

### What Is and Why ElectronJS?
Electron is a framework for building desktop applications with web technologies.
This helps us develop cross-platform applications by using existing web technologies. You don't need specific skills, for most cases, to develop apps with Electron. If you are a web developer then you can build desktop applications using ElectronJs.
Basically, it’s a Browser you can do everything you can with a browser and more.

### ElectronJs Features
1. <b>Security</b> - Data stays locally in the system, hence you can ensure data security.
2. <b>Hardware accessibility</b> - Developers can get complete access to all hardware-level access APIs exposed over the JavaScript/Plugin.
3. <b>Performance</b> - If proper care is taken while developing (load only what you need), ElectronJS can show some great gains in the terms of performance when compared to native applications. ElectronJS saves a lot of time and provides more options to play with or develop by having a single code base for all the major platforms.
4. <b>Code and App Management</b> - No need to maintain different teams for each platform, Single codebase
5. <b>Reusability</b> - As a single code base, can be used for web and desktop apps both.
6. <b>Deployment and build</b> - Using electron-packager and other packages it is very easy.
7. <b>Cost and Time</b> - Saving in both cost and time due to single code base
8. <b>UI / UX</b> - With web technologies, you are open to multiple technologies that provide great User Interface (UI) & User Experience (UX) to all your users with great comfort. Also, you can be sure that you are providing the same experience to all your users across different platforms.

### Application architecture ==
Electron consists of three main pillars:
* Chromium is an open-source part of Chrome for displaying web content.
* Node.js for working with the local filesystem and the operating system.
* Custom APIs for working with often-needed OS native functions.
Developing an application with Electron is like building a Node.js app with a web interface or building web pages with seamless Node.js integration.

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/node-chromium.jpg" width="600" align="center" alt="app-arch"/>
</p>

### Performing Culture
The Electron app may be categorized into two main processes, namely, the Main and Renderer process.

#### Main Process:
Every Electron app has exactly one main process aka “browser process”.
The main process is responsible for creating windows by using BrowserWindow instances. Individual BrowserWIndow instance renders a web page in its renderer process. Destroying a BrowserWindow instance implies that the corresponding renderer process is also terminated.
It includes/handles:
* Native functionality such as creating menus, trays, notifications, etc.
* Creating renderer processes
* Full Node API
* Serves as the entry point to your application

#### Renderer Process:
A renderer process is simply a new browser window inside your application. There is a single main process that is responsible for maintaining multiple renderer processes. Each renderer process manages the webpage and its scripts running inside it. 
* You can have multiple renderer processes
* They can be hidden and run in the background
* They each have their own process

Electron is still very similar to Chromium. In Chromium, each tab is a renderer process while the overall window is the main process.
In Electron we have the main process which you don’t really see, and each window we create is a renderer process.

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/main-renderer.png" align="center" alt="Renderer" />
</p>

### Most popular Electron apps
1. <b>Visual Studio code:</b> This is a popular open-source IDE developed by Microsoft.
2. <b>Slack:</b> This is a cross-platform chat application used by many companies to manage their messaging and event notification needs.
3. <b>Skype:</b> Skype is one of the most popular applications for chatting and video calls.
4. <b>Whatsapp Desktop:</b> The most downloaded messenger app, WhatsApp, is also using Electron and NodeJS. It is an open-source messaging client that runs on Mac, Windows and Linux. 
5. <b>WordPress Desktop:</b> most popular content management system (CMS), powering more than 35% of all websites on the internet! 
6. <b>Atom:</b> Most popular text editor
7. <b>Microsoft Teams:</b> Persistent chat-based collaboration platform complete with document sharing, online meetings, and many more extremely useful features for business communications
and many more..

### Building Simple Electron App

#### Prerequisites
Before proceeding with Electron you need to have Node.js.
To check that Node.js was installed correctly, type the following commands in your terminal client:<br/>

`node -v` <br/>
`npm -v`

The commands should print the versions of Node.js and npm accordingly. If both commands succeed, you are all set to proceed further.<br/>
If not succeeded, install NodeJs from [https://nodejs.org/en/download/ Download NodeJs]

#### Creating application
From a development perspective, an Electron application is essentially a Node.js application. This means that the starting point of your Electron application will be a *package.json* file like in any other Node.js application. 

##### Install Electron
Create a folder for your project and install Electron there:

     mkdir first-electron-app && cd first-electron-app
     npm init -y
     npm i --save-dev electron
     
##### Create the main script
The main script specifies the entry point of your Electron application (in our case, the main.js file) that will run the Main process. Your *main.js* script should look as shown below.
<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/wiki-electron-main.PNG" align="center"/>
</p>

What is going on above?

<b>Line 1:</b> First, you import the app and BrowserWindow modules of the electron package to be able to manage your application's lifecycle events, as well as create and control browser windows.

<b>Line 2:</b> Second, you import the path package which provides utility functions for file paths.

<b>Line 4:</b> After that, you define a function that creates a new browser window with a preload script, loads index.html file into this window (line 13, we will discuss the file later).

<b>Line 16:</b> You create a new browser window by invoking the createWindow function once the Electron application is initialized.

<b>Line 19:</b> You add a new listener that creates a new browser window only if the application has no visible windows after being activated. For example, after launching the application for the first time, or re-launching the already running application.

<b>Line 26:</b> You add a new listener that tries to quit the application when it no longer has any open windows. This listener is a no-op on macOS due to the operating system's window management behavior.

##### Create web page
This is the web page you want to display once the application is initialized. This web page represents the Renderer process. You can add any HTML sample template. Your *index.html* should look as shown below. (This HTML content entirely depends on your choice, shown in the image is for your reference)

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/wiki-electron-index.PNG" align="center"/>
</p>

##### Creating preload script
Your preload script (in our case, the preload.js file) acts as a bridge between Node.js and your web page. It allows you to expose specific APIs and behaviors to your web page rather than insecurely exposing the entire Node.js API. In this example, we will use the preload script to read version information from the process object and update the web page with that info.


    window.addEventListener("DOMContentLoaded", () => {
      const replaceText = (selector, text) => {
        const element = document.getElementById(selector);
        if (element) element.innerText = text;
     };
     for (const type of ["chrome", "node", "electron"]) {
      replaceText(`${type}-version`, process.versions[type]);
     }});
     
     
##### What's going on above?

1. <b>On line 1:</b> First you define an event listener that tells you when the web page has loaded

2. <b>On line 2:</b> Second you define a utility function used to set the text of the placeholders in the index.html*

3. <b>On line 7:</b> Next you loop through the list of components whose version you want to display

4. <b>On line 8:</b> Finally, you call replaceText to look up the version placeholders in index.html and set their text value to the values from process.versions

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/wiki-electron-preload.PNG" align="center"/>
</p>

##### Modify your package.json
Your Electron application uses the package.json file as the main entry point (as any other Node.js application). The main script of your application is main.js, so modify the package.json file accordingly:

    {
      "name": "first-electron-app",
      "version": "0.1.0",
      "author": "Shruthi M",
      "description": "Sample Electron app",
      "main": "main.js",
      "scripts": {
         "start": "electron ."
      },
      "devDependencies": {
         "electron": "^12.0.5"
      }
   }

Finally, your folder structure looks like this:

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/folder-structure.PNG" align="center"/>
</p>

Run the application using the command:<br/>
      `npm start`

If you have followed all the instructions properly, you can be able to see the electron application window will be launched on your screen, as shown in the below screenshot. 
The application launched in the center is your first electron application.

<p align="center">
     <img src="https://github.com/ShruthiMallaiah/All-about-ElectronJs/blob/main/ElectronJS%20and%20Why%20Should%20You%20Use%20It/Images/Final-output.PNG" width="800"/>
</p>

Hurray!! You have successfully built your first Electron app. Lets get to know about few benefits and drawbacks about ElectronJs.

### Benefits of using ElectronJs to build desktop applications
* Work on all platforms, including Linux
* Low barrier to entry — devs with web skills can reuse them
* Various OS integrations, including tray applets, media keys, etc
* Large community of developers and users
* Automatic updates
* Applications written in Electron have a better native feel compared to web versions, you can expect to be more enjoyable for the users.

### Downsides to using Electron to build applications
* Every app comes with the entire runtime
* Some apps are of poor quality
* Large download sizes
* High memory usage
 
Never stop learning, because life never stops teaching...!!

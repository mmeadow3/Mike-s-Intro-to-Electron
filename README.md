# Mikes-Intro-to-Electron

1. Create a package.json with npm init
2. If not already installed, install electron -g
3. Then "npm install electron-prebuilt --save-dev"
4. In the package.json, make a start script with the value "electon ."
5. "npm start" will open up window defined in main.js
6.  point window to desired file path  => win.loadURL(`file://${__dirname}/index.html`)
  6. in this case it is index.html

### Want some fresh styling???
## Of Course You Do!

[Go get Some Photon!](http://photonkit.com/)

## "Attempting to be able to deploy"
1. npm install electron-packager --save-dev
2. add
```
"build": "electron-packager . MyApp" to scripts in json, then "npm run build"
```
 2. this will create a folder named "MyApp-darwin-x64"
3. in command line run "open ."  <-- This will take you to a clickable app in finder

## Want to change that boring icon?
1. find a suitable .icns image
2. add this line to your package.json.  main.png.icns is the new image
```
"build": "electron-packager . MyApp && cp main.png.icns MyApp-darwin-x64/MyApp.app/Contents/Resources/electron.icns
```
## We need to ignore certain things like node_modules
1. just add --ignore=filesToIgnore after the name of your app in the json file

## How about some Privacy for your app
1. npm install asar --save-dev
2. go to scripts in package.json
3. add
```
"package": "asar pack MyApp-darwin-x64/MyApp.app/Contents/Resources/app MyApp-darwin-x64/MyApp.app/Contents/Resources/app.asar",
```
4. npm run package


# Always have to delete and rebuild using npm run build

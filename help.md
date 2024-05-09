# NOTE: In this project we r using VERSION 49.0.
- Keep in mind which vesion u r using for EXPO router in ur vscode and EXPO GO in phone, Versions should be same.
- And whatever packages u r installing all of those should of same versions too.
- https://docs.expo.dev/router/installation/#manual-installation

## create the expo app with below command
```
npx create-expo-app
```
## remove unwanted files
- app, components, constants, hooks, scripts, tsconfig.json

## create a App.js with code 
```
import { StatusBar } from "react-native";
import { StyleSheet, Text, View } from "react-native";

export default function App() {
    return (
        <View style={styles.container}>
        <Text>Employee App</Text>
        </View>
    );
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        backgroundColor: "#fff",
        alignItems: "center",
        justifyContent: "center",
    },
});
 
```
## create babel.config.js with below code
```
module.exports = function (api) {
    api.cache(true);
    return {
      presets: ['babel-preset-expo'],
      plugins: [
        'expo-router/babel',
        ['@babel/plugin-transform-class-properties', { loose: true }],
        ['@babel/plugin-transform-private-methods', { loose: true }],
        ['@babel/plugin-transform-private-property-in-object', { loose: true }]
      ],
    };
  };
```
## install the babel plugins after creating the file 
```
npm install --save-dev @babel/plugin-transform-private-methods
```
## Check if it's working or not by running the below comand 
```
npx expo start
```
## If it's not working run the below command
```
npx cross-env BABEL_SHOW_CONFIG_FOR=/home/pandey/pallavi/Attendance/employee-app/node_modules/react-native/Libraries/Debugging/DebuggingOverlayRegistry.js npx expo start
```

<hr>
-----------------------------------------Continue With Video--------------------------------------
<hr>



- when my icons are not loaded
  - https://stackoverflow.com/questions/57349431/error-with-expo-fontfamily-material-community-is-not-a-system-font-and-has-not

  - `rm -rf ./node_modules/expo/node_modules/expo-font/`
    - this fixed my issues
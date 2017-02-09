React Native 101 - Workshop 2 - Plugins
===

React Native plugins come in two different flavours - pure Javascript, or Native code. You can install a pure Javascript library from npm and use it immediately in the app. These can also be included in dynamic code push updates sent out to live applications in production. Native code libraries require an additional linking step which automatically scripts a number of changes to your native application to modify the end result binary, including any additional native code. Most plugins will also document steps for manual linking should something go wrong in the automated process.

If using an emulator to follow this workshop, make sure your front and back camera are associated with your computer's webcam in AVD Manager.

Adding a plugin
---

1. `cd Back2Base`
2. `npm install react-native-camera --save`
3. `react-native link react-native-camera`

The `--save` flag here is extremely important. Without this, our plugin would not be saved to our packages.config allowing us to redownload our dependencies if needed (i.e. if not committing them to source control).

Importing the plugin
---

Add the following to `index.android.js` below existing imports:

`import Camera from 'react-native-camera';`

Taking a photo!
---

1. Replace the contents of `render()` index.android.js with:
```
return (
  <View style={styles.container}>
    <Camera
      ref={(cam) => {
        this.camera = cam;
      }}
      style={styles.preview}
      aspect={Camera.constants.Aspect.fill}>
      <Text style={styles.capture} onPress={this.takePicture}>[CAPTURE]</Text>
    </Camera>
  </View>
);
```

Ref parmeters allow us to save a reference to a component that can be called elsewhere in your Javascript. This is useful for calling methods on those components, such as the `capture()` method we'll need to call in this case.

2. Add the following method to the component:

```
takePicture = () => {
  this.camera.capture()
    .then((data) => console.log(data))
    .catch(err => console.error(err));
}
```

3. Replace your styles as follows:

```
const styles = StyleSheet.create({
  container: {
    flex: 1
  },
  preview: {
    flex: 1,
    justifyContent: 'flex-end',
    alignItems: 'center',
    height: Dimensions.get('window').height,
    width: Dimensions.get('window').width
  },
  capture: {
    flex: 0,
    backgroundColor: '#fff',
    borderRadius: 5,
    color: '#000',
    padding: 10,
    margin: 40
  }
});
```

Try it out!
---

1. `react-native run-android`
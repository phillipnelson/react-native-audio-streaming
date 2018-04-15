
# react-native-audio-streaming

## Features

- Background audio streaming of remote stream
- Control via sticky notification on android and media center on iOS
- Shoutcast/Icy meta data support
- Simple UI player component (if needed, an api to control the sound is available)
- Gapless playback for queue
- Control playback speed
- Playback rate


## Add Node Package

`$ npm install git+https://git@github.com/phillipnelson/react-native-audio-streaming.git --save`


### Installation steps for iOS 

Choose one of three options:

#### 1. Cocoapods installation

1. add `pod 'RNAudioStreaming', :path => '../node_modules/react-native-audio-streaming'` to `Podfile`
2. run `pod install`


#### 2. Mostly automatic installation

`$ react-native link react-native-audio-streaming`

Go to `node_modules` ➜ `react-native-audio-streaming` => `ios` => `Pods` and drag/drop `Pods.xcodeproj` to the Libraries folder in your XCode project.

In XCode, in the project navigator, select your project. Add `libReactNativeAudioStreaming.a` and `libStreamingKit.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`


#### 3. Manual installation

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-audio-streaming` => `ios`
   - run `pod install` to download StreamingKit dependency
   - add `ReactNativeAudioStreaming.xcodeproj` to the Libraries folder in your XCode project
   - add `Pods/Pods.xcodeproj` to the Libraries folder in your XCode project
3. In XCode, in the project navigator, select your project. Add `libReactNativeAudioStreaming.a` and `libStreamingKit.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Run your project (`Cmd+R`)



### Add Header Search Paths

Make sure `$(SRCROOT)/../node_modules/react-native-audio-streaming/ios` is added to your project's `Header Search Paths` within the `Build Settings` section.


### Enable Audio Background Mode

2. Update Info.plist file of your Xcode project and add audio background mode

```xml
    <key>UIBackgroundModes</key>
    <array>
      <string>audio</string>
    </array>
```


## Usage

### Basic Playback

```javascript
import { ReactNativeAudioStreaming } from 'react-native-audio-streaming';

const url = "http://lacavewebradio.chickenkiller.com:8000/stream.mp3";
ReactNativeAudioStreaming.pause();
ReactNativeAudioStreaming.resume();
ReactNativeAudioStreaming.play(url, {showIniOSMediaCenter: true, showInAndroidNotifications: true});
ReactNativeAudioStreaming.stop();
```


### Playback Rate

```javascript
ReactNativeAudioStreaming.setRate(1.25);
```


### Player UI

```javascript
import { Player } from 'react-native-audio-streaming';

class PlayerUI extends Component {
  render() {
    return (
        <Player url={"http://lacavewebradio.chickenkiller.com:8000/stream.mp3"} />
    );
  }
}
```


## TODO - @phillipnelson

- [ ] Lock screen controls
- [ ] Lock screen artwork and metadata
- [ ] Persistent playlist
- [ ] Playlist cache controls
- [ ] Local persistent cache
- [ ] Callbacks for playlist management


## Future - @phillipnelson

- [ ] Android feature parity
- [ ] Add tests


## Additional Notes

### Other RN audio projects

- [jsierles/react-native-audio](https://github.com/jsierles/react-native-audio) to play local audio and record
- [zmxv/react-native-sound](https://github.com/zmxv/react-native-sound) to play local audio with more controls

### Credits

- Using StreamingKit version from https://github.com/podverse/StreamingKit featuring Playback control
- Android version based on the work of @EstebanFuentealba https://github.com/EstebanFuentealba/react-native-android-audio-streaming-aac
- iOS version based on the work of @jhabdas https://github.com/jhabdas/lumpen-radio

See also the list of [contributors](https://github.com/tlenclos/react-native-audio-streaming/graphs/contributors) who participated in this project.

### License

This project is licensed under the MIT License - see the LICENSE file for details


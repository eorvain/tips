# tips XCode

## Clean Hard drive XCode

https://apple.stackexchange.com/questions/287307/reduce-size-of-the-xcode-application

1. Derived Data Xcode keeps data about your projects which includes index, build output and logs. Go to ~/Library/Developer/Xcode/DerivedData/ and delete the folders for projects that you no longer need to keep this data around for.

2. iOS Device Support Xcode is storing information about the devices you have used for development. Delete the data no longer needed in ~/Library/Developer/Xcode/iOS DeviceSupport/.

3. Archives Delete the one’s you don’t need in the Organizer, or go to ~/Library/Developer/Xcode/Archives/ to delete them in bulk. Be careful not to delete archives for which you still need the dSYM data for debugging.

4. Simulators Simulators are stored under ~/Library/Developer/CoreSimulator/Devices. For each version of iOS you are building for.

5. Documentation Browse and delete unnecessary data under ~/Library/Developer/Shared/Documentation/DocSets.

## Clean Simulator

Delete unavailable Simulator OS
```
xcrun simctl delete unavailable
```

Delete all installed applications
```
xcrun simctl erase all
```

## Xcode compatibility with iOS
Path to simulator of an Xcode :
```
cd /Applications/Xcode9.0.0.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/
```
Path to image of devices :
```
cd ~/Library/Developer/Xcode/iOS\ DeviceSupport/
```

From a device image to an Xcode (device->Xcode)
```
sudo ln -s \
~/Library/Developer/Xcode/iOS\ DeviceSupport/10.0\ \(14A5309d\) \
/Applications/Xcode9.0.0.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/10.0
```
Froma a new Xcode to an old Xcode (old Xcode -> new Xcode) 
```
sudo ln -s /Applications/Xcode9.4.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/11.3 /Applications/Xcode9.0.0.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/11.3
```

## Xcode Path
### Xcode archive
```
open ~/Library/Developer/Xcode/Archives/
```
### Xcode physical image Simulateur
```
open ~/Library/Developer/Xcode/iOS\ DeviceSupport/
```

### XCode Simulator paths
```
open ~/Library/Developer/CoreSimulator
```

### Code snippets
```
open ~/Library/Developer/Xcode/UserData/CodeSnippets
```

# Lines of code

```
brew install cloc
cd path/to/project/
cloc .
```

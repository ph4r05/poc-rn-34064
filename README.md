## PoC for React-native #34064

PoC for https://github.com/facebook/react-native/pull/34064 demonstrating iOS build failure on React-RCTText. Expo modules are used.

Build:
```bash
yarn install
npx pod-install
```

## How to recreate this repo

```bash
npx react-native init rnProc --version 0.68.2  # has to use this version as 0.69.0 fails
npx install-expo-modules
```

- Migrate to 0.69.0 with the [migration guide](https://react-native-community.github.io/upgrade-helper/?from=0.68.2&to=0.69.0)

```
/bin/rm -rf node_modules ios/Pods ios/Podfile.lock
yarn install
npx pod-install
```

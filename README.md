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

- Migrate to 0.69.0 according to the [migration guide](https://react-native-community.github.io/upgrade-helper/?from=0.68.2&to=0.69.0)

```
/bin/rm -rf node_modules ios/Pods ios/Podfile.lock
yarn install
npx pod-install
```

## Testing unreleased expo

```bash
git clone --recursive https://github.com/expo/expo.git /tmp/expo && cd /tmp/expo
npm run setup:native
```

Edit `package.json`
```json lines
"dependencies": {
  "expo": "file:/tmp/expo/packages/expo"
}
```

Run
```bash
yarn install
npx pod-install
```

## Related issues
- https://github.com/expo/expo/issues/16283
- https://github.com/facebook/react-native/issues/33815
- https://github.com/facebook/react-native/issues/33976
- https://github.com/facebook/react-native/pull/34064



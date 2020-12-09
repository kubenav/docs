# Development

kubenav requires [Node v8.6.0](https://nodejs.org/) or later, and NPM version 5.6.0 or later (which is usually automatically installed with the required version of Node).

If there is a previous installation of the Ionic CLI installed, it will need to be uninstalled due to a change in package name for ionic/cli:

```sh
npm uninstall -g ionic
```

If you have Node and NPM installed, install Ionic CLI:

```sh
npm install -g @ionic/cli
```

Besides Node, kubenav requires [Go 1.14](https://golang.org) or later and [Go mobile](https://github.com/golang/go/wiki/Mobile), which can be installed using the following commands:

```sh
go get -u golang.org/x/mobile/cmd/gomobile
go install golang.org/x/mobile/cmd/gomobile
gomobile init
```

To build the Electron version of kubenav, install the [go-astilectron-bundler](https://github.com/asticode/go-astilectron-bundler):

```sh
go get -u github.com/asticode/go-astilectron-bundler/...
go install github.com/asticode/go-astilectron-bundler/astilectron-bundler
```

To build the iOS version of kubenav ensure that you have [Xcode](https://developer.apple.com/xcode/) and [CocoaPods](https://cocoapods.org) installed. For the Android version you need the Android SDK, which can be installed via [Android Studio](https://developer.android.com/studio) and the [NDK](https://developer.android.com/ndk/). Also ensure that the `ANDROID_HOME` and `ANDROID_NDK_HOME` environment variables are set.

Clone the repository, login to GitHub packages and install the required dependencies:

```sh
git clone git@github.com:kubenav/kubenav.git
cd kubenav

npm install
```

You must build the kubenav project at least once before running on any native platform:

```sh
ionic build
```

You may then build the relevant mobile platform you require

```sh
make bindings-android
make bindings-ios
```

To use kubenav in your browser you need to build and start the server. The server listening on port `14122`:

```sh
make build-server && ./bin/server
```

Now you can start the app and open [localhost:8100](http://localhost:8100) in your browser:

```sh
ionic serve
```

Every time you perform a build (e.g. `ionic build`) that changes your web directory (default: `build`), you'll need to copy those changes down to your native projects:

```sh
npx cap sync
```

The native iOS and Android projects are opened in their standard IDEs (Xcode and Android Studio, respectively). Use the IDEs to run kubenav:

```sh
npx cap open ios
npx cap open android
```

You can also run the native iOS or Android app with live reloading:

```sh
ionic capacitor run android -l --address=0.0.0.0
ionic capacitor run ios -l --address=0.0.0.0
```

To build the Electron version of kubenav run `make build-electron`. The app can be found in the `cmd/electron/output/<PLATFORM>-amd64` folder:

```sh
make build-electron
```

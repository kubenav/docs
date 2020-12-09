# Releases

Every new release is created from the `master` branch. To create a new release the `version` field in the `package.json` file must be updated and a new tag must be set. This process is automated via a [`Makefile`](https://github.com/kubenav/kubenav/blob/master/Makefile):

```sh
make release-patch
make release-minor
make release-major
```

When the tag is pushed the changelog will be generated via GitHub Action and saved to the [CHANGELOG.md](./CHANGELOG.md) file. When the changelog was generated a new GitHub release can be created with the following naming scheme and the changelog for the current tag as description:

```txt
Version <TAG> (yyyy-mm-dd)
```

After the release was created another GitHub Action is executed to create the Electron app for macOS, Linux and Windows via [go-astilectron-bundler](https://github.com/asticode/go-astilectron-bundler). These files are added to the corresponding release. The following files are available for each release:

- `kubenav-darwin-amd64.tar.gz`
- `kubenav-linux-amd64.tar.gz`
- `kubenav-windows-amd64.tar.gz`

Next to the binaries for the desktop version, we are also running a GitHub Action to push a new Docker image to [Docker Hub](https://hub.docker.com/r/kubenav/kubenav) with the following name: `kubenav/kubenav:<TAG>`.

The native iOS and Android app is built manually and submitted to the App Store and Google Play. To prepare the native app, run the following commands:

```sh
make bindings-android
make bindings-ios

export REACT_APP_VERSION=<TAG>

ionic build

npx cap sync

npx cap open ios
npx cap open android
```

In the standard IDE for iOS (Xcode) and Android (Android Studio) run a clean build and follow the steps to publish the app.

## Beta Release

We are building the binaries for each submitted PR and on a [nightly schedule](https://github.com/kubenav/kubenav/actions?query=workflow%3ABuild+event%3Aschedule). To test new feature you can always download the binaries from the corresponding GitHub Action.

We are also pushing a new Docker image for each master commit to [Docker Hub](https://hub.docker.com/r/kubenav/kubenav). The images are taged with the corresponding commit hash.

To publish a new beta version for iOS and Android you can follow the same steps as for a normal release, except that you have to run `make release-beta`. The beta versions are available via [Apple Testflight](https://testflight.apple.com/join/RQUFGkHi) and [Google Play](https://play.google.com/apps/testing/io.kubenav.kubenav).

## Changelog

The changelog will be generated via GitHub Action, but sometimes it is useful to generate the `CHANGELOG.md` file locally, before a new tag is created. This can be done with the following command:

```sh
docker run -it --rm -v "$(pwd)":/usr/local/src/your-app ferrarimarco/github-changelog-generator --user=kubenav --project=kubenav --token=<TOKEN>
```

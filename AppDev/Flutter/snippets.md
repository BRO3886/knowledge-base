# Useful Code Snippets
Random useful code snippets I'd have to reference time and again

## Table of Contents
- [Useful Code Snippets](#useful-code-snippets)
  - [Table of Contents](#table-of-contents)
  - [Github Action: APK Gen](#github-action-apk-gen)

## Github Action: APK Gen

```yaml
name: Flutter CI
# when the workflow should run
on:
  push:
    branches:
      - master
# a workflow is made up of multiple jobs
jobs:
  build:
    # selecting the machine to run the job on
    runs-on: ubuntu-latest
    # a job contains a sequence of tasks called steps
    steps:
      # setting up the environment to build apk
      - uses: actions/checkout@v2
      - uses: actions/setup-java@v1
        with:
          java-version: '12.x'
      # we are going to use subosito's flutter action https://github.com/marketplace/actions/flutter-action
      # setup flutter env
      - uses: subosito/flutter-action@v1
        with:
          flutter-version: 'optional: specify version else remove'
        # optional environment variables
        env:
          # KEY_JKS: ${{secrets.KEY_JKS}}
          KEY_PASSWORD: ${{secrets.KEY_PASSWORD}}
          STORE_PASSWORD: ${{secrets.STORE_PASSWORD}}
          # run: echo $KEY_JKS > key.jks
      # after setup, start running flutter commands
      # get packages
      - run: flutter pub get
      - run: flutter packages get
      # check dart code for errors
      #- run: flutter analyze .
      # check formatting issues
      #- run: flutter format --set-exit-if-changed .
      # build apk
      - run: flutter build apk
      #upload apk to artifact. We will use https://github.com/actions/upload-artifact for this
      - uses: actions/upload-artifact@v1
        with:
          name: release-apk
          path: build/app/outputs/apk/release/app-release.apk
      #send artifact to telegram channel
      - uses: appleboy/telegram-action@master
        with: 
          to: ${{secrets.TELEGRAM_CHANNEL}}
          token: ${{secrets.TELEGRAM_BOT_APIKEY}}
          document: build/app/outputs/apk/release/app-release.apk
          message: |
            some message to accompany APK
```
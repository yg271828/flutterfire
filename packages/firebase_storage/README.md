# Firebase Cloud Storage for Flutter

[![pub package](https://img.shields.io/pub/v/firebase_storage.svg)](https://pub.dev/packages/firebase_storage)

A Flutter plugin to use the [Firebase Cloud Storage API](https://firebase.google.com/products/storage/).

For Flutter plugins for other Firebase products, see [README.md](https://github.com/FirebaseExtended/flutterfire/blob/master/README.md).

## Usage

To use this plugin, add `firebase_storage` as a [dependency in your pubspec.yaml file](https://flutter.io/platform-plugins/).

### Logging

If you wish to see status events for your upload tasks in your logs, you should listen to the `StorageUploadTask.events` stream.  
This could look like the following if you are using `StorageReference.putData`:

```dart
final StorageReference storageReference = FirebaseStorage().ref().child(path);

final StorageUploadTask uploadTask = storageReference.putData(data);

final StreamSubscription<StorageTaskEvent> streamSubscription = uploadTask.events.listen((event) {
  // You can use this to notify yourself or your user in any kind of way.
  // For example: you could use the uploadTask.events stream in a StreamBuilder instead
  // to show your user what the current status is. In that case, you would not need to cancel any
  // subscription as StreamBuilder handles this automatically.

  // Here, every StorageTaskEvent concerning the upload is printed to the logs.
  print('EVENT ${event.type}');
});

// Cancel your subscription when done.
await uploadTask.onComplete;
streamSubscription.cancel();
```

## Getting Started

See the `example` directory for a complete sample app using Firebase Cloud Storage.

## Issues and feedback

Please file FlutterFire specific issues, bugs, or feature requests in our [issue tracker](https://github.com/FirebaseExtended/flutterfire/issues/new).

Plugin issues that are not specific to Flutterfire can be filed in the [Flutter issue tracker](https://github.com/flutter/flutter/issues/new).

To contribute a change to this plugin,
please review our [contribution guide](https://github.com/FirebaseExtended/flutterfire/blob/master/CONTRIBUTING.md)
and open a [pull request](https://github.com/FirebaseExtended/flutterfire/pulls).

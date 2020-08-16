## 2.0.0-dev.1

* See the `firebase_auth` plugin changelog.

## 1.1.8

* Update lower bound of dart dependency to 2.0.0.

## 1.1.7

* Use package:plugin_platform_interface

## 1.1.6

* Make the pedantic dev_dependency explicit.

## 1.1.5

- Fixed typo on private method name.

## 1.1.4

- **Breaking change**: Added missing `app` parameter to `confirmPasswordReset`.
  (This is an exception to the usual policy of avoiding breaking changes since
  `confirmPasswordReset` is a new API and doesn't have clients yet.)

## 1.1.3

- Added support for `confirmPasswordReset`

## 1.1.2

- Remove the deprecated `author:` field from pubspec.yaml

## 1.1.1

- Fixed crash when platform returns an auth result where `additionalUserInfo`
  is not provided.

## 1.1.0

- Added type `PlatformOAuthCredential` for generic OAuth providers.

## 1.0.0

- Initial open-source release.

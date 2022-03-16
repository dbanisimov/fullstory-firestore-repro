# Fullstory Firestore AJAX recording issue repro

## Setup
This repo is configured with a test Firebase project `fullstory-firestore-repro` and a test FS org. It is OK to use it as is, but you might want to replace it with your config values.

* Change `_fs_org` value if needed
* Change `firebaseConfig` value if needed

You also need to have access to an FS org to switch on and off the AJAX recording

## Running the repro

* [optional] Uncomment line with `connectFirestoreEmulator` to use a local Firestore emulator. The issue affects both emulated and real Firestores
* Run emulators with `firebase emulators:start --import=emulators`
* Enable AJAX recording in your FS settings
* Open `localhost:5000` and click on "Load a document from Firestore"
* The request will timeout after ~10sec. This can be confirmed by the error message in the console
* Disable AJAX recording in your FS settings
* Reload the page `localhost:5000` and try to load the Firestore document again.
* The request will succeed this time.
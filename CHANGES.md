# Release notes
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## 2023-10-19

### photos-app:0.3.2
* Images should be resized to fit the dashboard frame, instead of potential cropping
* App/Device names are auto-updated with the selected album name when clicking "Done" in the App.
* Image/Video processing validates metadata keys directly instead of relying on Groovy truth of their values

## 2021-07-25

### photos-app:0.3.1
* Enhancement: #1 - if enabled, shuffle album after loading photos (for first iteration)

## 2021-06-11

### photos-app:0.3.0
* Refresh interval can be in seconds or minutes
* New preference to shuffle album on each cycle
* Support new device commands next, previous, pause, resume

### photos-device:0.1.0
* New commands: next, previous, pause, resume

## 2021-05-25

### photos-app:0.2.1
* Bugfix: cron exception on new installs

## 2021-05-21

### photos-app:0.2.0
* Change HTML tag depending on photo of video media
* Send event to update device "mediaType" attribute

### photos-device:0.0.2
* New attribute: mediaType

## 2021-05-17

### photos-app:0.1.1
* Bugfix: nightly refresh runs every second for the hour of 11pm

### photos-app:0.1.0
* Set refresh interval via App preferences
* Preferences toggle to refresh list of photo IDs in album nightly (at 11pm)

## 2021-05-15

### photos-app:0.0.2
* Initial implementation -- authorization, API queries

### photos-device:0.0.1
* Initial implementation -- image attribute, refresh command
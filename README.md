# PyTorch on Android

PyTorch on Android is a project to demo how to use [PyTorch](https://pytorch.org/) to build an Android mobile application doing real time object classification.

![demo](https://media.giphy.com/media/oOLw8fRszs5Ris7rVj/giphy.gif)

## Goal

Make it easier to ship and test your neural network model in PyTorch on mobile devices.

## Documentation

We created a developer guide on [how to ship a convolutional neural network on Android with PyTorch and Android Studio](https://github.com/cedrickchee/data-science-notebooks/blob/master/notebooks/deep_learning/fastai_mobile/README.md). Check it out!

### Step by Step Guide

We'll walk you through every step, from problem all the way to building and deploying the Android app to mobile phones.

## Features, Funtionalities and TODO

- [X] iOS (Swift/Objective-C/C++) with Caffe2
- [x] Test SqueezeNet v1.1 model with your own video stream from camera
- [x] Live (real-time) detection
- [ ] Performance optimization
- [ ] Test build in models (MobileNetV2, ShuffleNet) with your own video stream from camera
- [ ] Download your own model on the fly and test it
- [ ] Manage models locally on your Android device
- [ ] Memory consumption and time elapse data
- [ ] Overall control on every layer (from beginner to expert)
- [ ] Warm community and welcome to contribute
- [ ] Transfer learning SqueezeNet with new datasets (i.e. insect species, not hotdog)
- [ ] New classifier for insect species dataset using pre-trained ImageNet weights (transfer learning)
- [ ] Upload pre-trained models
- [ ] Bug fixes
- [ ] Fix intermittent crashes

## Android Project

You can download the Android project source code by running this command:

`git clone https://github.com/cedrickchee/pytorch-android.git`

## Android Development Environment

### Dependencies

- Android Studio: 3.0 and above
- Android SDK
- Android NDK
- CMake Android SKD component
- Gradle 3.x

## Tests

| Device             | Network       |  FPS (^)  |
| ------------------ | ------------- | --------- |
| Google Nexus 6P    | SqueezeNet    |  3.0      |
| Samsung Note 8     | SqueezeNet    |  _TBD_    |
| Samsung Galaxy S7  | SqueezeNet    |  5.8      |
| Google Pixel       | SqueezeNet    |  5.7      |

_Note:_
_^ the number of FPS is subjective to the camera photo (image) size you send to the mobile device as well as type of the device._

## Demo

If building this repo is too much of a trouble for you, we also plan to put this in Google Play Store (TBD).

## Performance

_TBD_

## Future Work

Scope of work for this project: _TBD_

## Other Useful Resources

- [PyTorch and the merged Caffe2 repo](https://github.com/pytorch/pytorch)

## Support

Feel free to ask any questions, from preparing development environment to debugging on Android Studio. We are happy to help you.

## License

This repository contains a variety of content; some developed by Cedric Chee, and some from third-parties. The third-party content is distributed under the license provided by those parties.

*I am providing code and resources in this repository to you under an open source license.  Because this is my personal repository, the license you receive to my code and resources is from me and not my employer.*

The content developed by Cedric Chee is distributed under the following license:

### Code

The code in this repository, including all code samples in the notebooks listed above, is released under the [MIT license](LICENSE). Read more at the [Open Source Initiative](https://opensource.org/licenses/MIT).

### Text

The text content of the book is released under the CC-BY-NC-ND license. Read more at [Creative Commons](https://creativecommons.org/licenses/by-nc-nd/3.0/us/legalcode).

# Image Manipulation and Async/Await Conversion Workshop

This project demonstrates the use of Expo APIs to manipulate images, access saved images, and convert then-based promise handling to async/await. The project is divided into three main tasks, each building on the previous one to enhance the functionality of an image-related feature in a React Native application.

## Table of Contents
- [Task 1: Resize a Photo and Convert it to PNG](#task-1-resize-a-photo-and-convert-it-to-png)
- [Task 2: Add Choosing from Image Gallery Option](#task-2-add-choosing-from-image-gallery-option)
- [Task 3: Implement Async/Await for NetInfo.fetch()](#task-3-implement-asyncawait-for-netinfofetch)
- [Bonus Task: Save Captured Images to the Device's Image Library](#bonus-task-save-captured-images-to-the-devices-image-library)
- [Testing](#testing)

## Task 1: Resize a Photo and Convert it to PNG

In this task, the goal is to update the `LoginScreen.js` file to intercept a photo after it has been taken using the `ImagePicker.launchCameraAsync()` method and process it with the Expo ImageManipulator API. The photo will be resized to 400x400 pixels and saved as a PNG file.

### Steps:
1. **Import the ImageManipulator API**: Import the `ImageManipulator` component from the Expo package into `LoginScreen.js`.
2. **Create an Async Function**: In the `RegisterTab` component, create a new async function called `processImage` that accepts `imgUri` as a parameter.
3. **Manipulate the Image**: Use the `ImageManipulator.manipulateAsync` method to create a new image from the `imgUri` with a width of 400px, and save it as a PNG.
4. **Update the Image URL**: Log the details of the processed image to the console and update the `imageUrl` state variable with the URI of the new image.
5. **Integrate the Function**: Replace the existing call to `setImageUrl` in the `getImageFromCamera` function with a call to `processImage`, passing the captured image URI as the argument.

## Task 2: Add Choosing from Image Gallery Option

This task extends the functionality by allowing users to choose an image from the device’s gallery instead of taking a new one with the camera.

### Steps:
1. **Add a Gallery Button**: Create a new `Button` component titled "Gallery" in the `RegisterTab` component.
2. **Create an Async Function**: Create an async function named `getImageFromGallery` to handle image selection from the gallery.
3. **Request Permissions**: Use the `ImagePicker` library to request access to the media library and store the return value.
4. **Open the Image Gallery**: If permission is granted, open the gallery using `ImagePicker.launchImageLibraryAsync` with editing enabled and a 1:1 aspect ratio.
5. **Process the Selected Image**: Log the details of the selected image and call the `processImage` function to resize and convert the image to PNG.

## Task 3: Implement Async/Await for NetInfo.fetch()

In this task, the focus is on updating the `MainComponent.js` file to use async/await for handling promises returned by the `NetInfo.fetch()` method.

### Steps:
1. **Create an Async Function**: Implement a new async function named `showNetInfo` in the `Main` component.
2. **Convert to Async/Await**: Move the code from the `useEffect` hook that handles `NetInfo.fetch()` into the new async function and convert the then-based promise handling to async/await.
3. **Update the useEffect Hook**: Replace the removed code in the `useEffect` hook with a call to the `showNetInfo` async function.

## Bonus Task: Save Captured Images to the Device's Image Library

As a bonus, implement functionality to save images captured using the `launchCameraAsync` method to the device's image library using the Expo Media Library module.

### Steps:
1. **Install the Media Library Module**: Install the module using `expo install expo-media-library`.
2. **Import the Module**: Import the `expo-media-library` into the `MediaLibrary` namespace.
3. **Save the Image**: Use the `MediaLibrary.saveToLibraryAsync()` method to save the processed image to the library.

## Testing

Ensure that each task is thoroughly tested:
- **Task 1**: Verify that the resized PNG image is created and logged to the console after capturing a photo.
- **Task 2**: Confirm that the Gallery button functions correctly and that selected images are resized and logged.
- **Task 3**: Test that the network connectivity type is displayed using the new async/await implementation.

---

This project serves as a hands-on practice for using Expo APIs and converting promise-based code to async/await, which is an essential skill for modern JavaScript development.


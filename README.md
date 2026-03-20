# Ex05 Image Carousel
## Date:20.03.2026

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
## index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Image Carousel</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h2>React Image Carousel</h2>

  <div class="carousel">
    <img id="carouselImage" src="https://images.unsplash.com/photo-1501785888041-af3ef285b470">
  </div>

  <div>
    <button onclick="prevImage()">Previous</button>
    <button onclick="nextImage()">Next</button>
  </div>

  <script src="script.js"></script>
</body>
</html>
```
## script.js
```
const images = [
  "https://images.unsplash.com/photo-1501785888041-af3ef285b470",
  "https://images.unsplash.com/photo-1500530855697-b586d89ba3ee",
  "https://images.unsplash.com/photo-1491553895911-0055eca6402d"
];

let index = 0;

function showImage() {
  document.getElementById("carouselImage").src = images[index];
}

function prevImage() {
  index = (index - 1 + images.length) % images.length;
  showImage();
}

function nextImage() {
  index = (index + 1) % images.length;
  showImage();
}
```
##  app.js
```
import React from "react";
import ImageCarousel from "./ImageCarousel";

function App() {
  return (
    <div>
      <ImageCarousel />
    </div>
  );
}

export default App;

```

## OUTPUT
<img width="1906" height="660" alt="image" src="https://github.com/user-attachments/assets/841c38ba-ed38-4570-acc2-0f879147f292" />


## RESULT
The program for creating Image Carousel using React is executed successfully.

# Digital Image Processing

# Feature Detection and Description

Here’s a simplified summary of the text:

This chapter focuses on understanding features in images and why they are important. Features are specific patterns in images that help identify and compare different parts of an image. For example, when you play a jigsaw puzzle, you find unique patterns in the pieces to assemble the puzzle. Similarly, computers use features to stitch images or create 3D models from photos.

Key Points:
- Flat Areas (like A and B): These are hard to locate because they look the same everywhere.
- Edges (like C and D): Easier to find but still not perfect because the pattern repeats along the edge.
- Corners (like E and F): Best features because they look unique and don’t repeat, no matter where you move them.
- Features like corners are great because they show maximum variation in all directions. Identifying these is called Feature Detection. Once features are found, they are described in detail so the computer can find the same feature in other images. This is called Feature Description.

With features detected and described, we can align images, stitch them together, or use them for other tasks. The chapter will explore algorithms in OpenCV to detect, describe, and match features.

**Harris Corner Detection in OpenCV**

The Harris Corner Detection algorithm identifies corners in images by analyzing intensity variations. OpenCV's `cv.cornerHarris()` function facilitates this detection.

### Key Points:
OpenCV has the function cv.cornerHarris() for this purpose. Its arguments are:

**img** - Input image. It should be grayscale and float32 type.
**blockSize** - It is the size of neighbourhood considered for corner detection
**ksize** - Aperture parameter of the Sobel derivative used.
**k** - Harris detector free parameter in the equation.

**Implementation Steps:**

1. **Convert Image to Grayscale and Float32:**

   ```python
   import cv2 as cv
   import numpy as np

   img = cv.imread('chessboard.png')
   gray = cv.cvtColor(img, cv.COLOR_BGR2GRAY)
   gray = np.float32(gray)
   ```

2. **Apply Harris Corner Detection:**

   ```python
   dst = cv.cornerHarris(gray, blockSize=2, ksize=3, k=0.04)
   ```

   - `blockSize`: Neighborhood size for corner detection.
   - `ksize`: Aperture parameter for the Sobel derivative.
   - `k`: Harris detector free parameter.

3. **Dilate Result for Marking Corners (Optional):**

   ```python
   dst = cv.dilate(dst, None)
   ```

4. **Threshold to Identify and Mark Corners:**

   ```python
   img[dst > 0.01 * dst.max()] = [0, 0, 255]
   ```

5. **Display the Result:**

   ```python
   cv.imshow('dst', img)
   if cv.waitKey(0) & 0xff == 27:
       cv.destroyAllWindows()
   ```

This process highlights detected corners in red on the original image.

**Subpixel Accuracy:**

For enhanced precision in corner localization, OpenCV offers the `cv.cornerSubPix()` function, which refines corner positions to subpixel accuracy.

For a comprehensive understanding and additional details, refer to the official OpenCV documentation. 

```python
import numpy as np
import cv2 as cv

filename = 'chessboard2.jpg'
img = cv.imread(filename)
gray = cv.cvtColor(img,cv.COLOR_BGR2GRAY)

# find Harris corners
gray = np.float32(gray)
dst = cv.cornerHarris(gray,2,3,0.04)
dst = cv.dilate(dst,None)
ret, dst = cv.threshold(dst,0.01*dst.max(),255,0)
dst = np.uint8(dst)

# find centroids
ret, labels, stats, centroids = cv.connectedComponentsWithStats(dst)

# define the criteria to stop and refine the corners
criteria = (cv.TERM_CRITERIA_EPS + cv.TERM_CRITERIA_MAX_ITER, 100, 0.001)
corners = cv.cornerSubPix(gray,np.float32(centroids),(5,5),(-1,-1),criteria)

# Now draw them
res = np.hstack((centroids,corners))
res = np.int0(res)
img[res[:,1],res[:,0]]=[0,0,255]
img[res[:,3],res[:,2]] = [0,255,0]

cv.imwrite('subpixel5.png',img)
```

---

**Shi-Tomasi Corner Detector & Good Features to Track**

The Shi-Tomasi Corner Detector is an improved method for finding corners in images, enhancing the earlier Harris Corner Detector. 

**Key Points:**

- **Purpose:** Identify important corners in images.

- **Improvement:** Uses the minimum of two values (λ₁, λ₂) to detect corners, offering better results than the Harris method.

**Using OpenCV's `cv.goodFeaturesToTrack()` Function:**

This function helps find strong corners in a grayscale image.

**Parameters:**

- **`maxCorners`:** Maximum number of corners to detect.

- **`qualityLevel`:** Threshold (0 to 1) to filter out weak corners.

- **`minDistance`:** Minimum distance between detected corners.

**Example Code:**

```python
import numpy as np
import cv2 as cv
from matplotlib import pyplot as plt

# Load image and convert to grayscale
img = cv.imread('blox.jpg')
gray = cv.cvtColor(img, cv.COLOR_BGR2GRAY)

# Detect corners
corners = cv.goodFeaturesToTrack(gray, 25, 0.01, 10)
corners = np.int0(corners)

# Draw circles around corners
for i in corners:
    x, y = i.ravel()
    cv.circle(img, (x, y), 3, 255, -1)

# Display the result
plt.imshow(img)
plt.show()
```

This script loads an image, converts it to grayscale, detects the top 25 corners using the Shi-Tomasi method, marks them with circles, and displays the result.

For a comprehensive understanding and additional details, refer to the official OpenCV documentation. 

# **Introduction to SIFT (Scale-Invariant Feature Transform)**

SIFT is a method used in computer vision to detect and describe local features in images. It identifies key points that are invariant to scale and rotation, making it effective for object recognition and image matching. 

SIFT (Scale-Invariant Feature Transform) is a popular algorithm in Digital Image Processing (DIP) used for detecting and describing key features in images. It is widely used in applications like object recognition, image stitching, and motion tracking because it is highly reliable and robust to changes in scale, rotation, and lighting.

**Key Features of SIFT:**

- **Scale-Invariance:**
SIFT can detect features in images regardless of their size. For example, it works whether an object appears small or large in the image.

- **Rotation-Invariance:**
SIFT features are unaffected by the orientation of the object. Even if the object is rotated in the image, the algorithm can still recognize the features.

- **Robust to Illumination Changes:**
SIFT is designed to handle variations in brightness and contrast, making it suitable for real-world scenarios.

**Implementation in OpenCV:**

OpenCV provides the `cv.SIFT_create()` function to create a SIFT detector object. This object can then be used to detect key points and compute their descriptors.

**Example Code:**

```python
import cv2 as cv

# Load the image
img = cv.imread('image.jpg')
gray = cv.cvtColor(img, cv.COLOR_BGR2GRAY)

# Initialize SIFT detector
sift = cv.SIFT_create()

# Detect keypoints and compute descriptors
keypoints, descriptors = sift.detectAndCompute(gray, None)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None)

# Display the result
cv.imshow('SIFT Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

This script loads an image, converts it to grayscale, detects SIFT key points and computes their descriptors, draws the key points on the original image, and displays the result.


# **Introduction to SURF (Speeded-Up Robust Features)**

**SURF (Speeded-Up Robust Features)** is a feature detection and description algorithm used in **Digital Image Processing**. It is designed to identify and match key features in images, like corners, edges, or blobs, and is known for being faster than SIFT while still being robust to changes in scale, rotation, and lighting.

---

### Key Points of SURF:

1. **Fast and Efficient**:
   - SURF is called "speeded-up" because it uses approximations and mathematical tricks to detect features much faster than SIFT.

2. **Scale-Invariant**:
   - It can find features in images regardless of size, making it suitable for objects that appear closer or farther in different images.

3. **Rotation-Invariant**:
   - SURF can handle rotated images, detecting the same features even if the object is turned.

4. **Robust to Lighting Changes**:
   - It works well even when there are variations in brightness and contrast.

---

### How SURF Works:

1. **Keypoint Detection**:
   - SURF detects keypoints using **Hessian matrix-based filters** to find regions with high intensity variations, like corners or blobs.

2. **Keypoint Description**:
   - Around each keypoint, SURF creates a descriptor based on local image gradients, which summarizes the region's characteristics.

3. **Matching**:
   - Descriptors from one image can be compared with those from another to find matching features.

---

### Applications of SURF:

- **Object Recognition**:
   Identify objects in images, even if their size or orientation changes.

- **Image Stitching**:
   Combine overlapping images into a panorama by matching features.

- **Tracking**:
   Follow objects or points in a video sequence.

---

### Example in OpenCV:

```python
import cv2 as cv

# Load the image
img = cv.imread('example.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the SURF detector
surf = cv.xfeatures2d.SURF_create(400)

# Detect keypoints and compute descriptors
keypoints, descriptors = surf.detectAndCompute(img, None)

# Draw the keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None, flags=cv.DRAW_MATCHES_FLAGS_DRAW_RICH_KEYPOINTS)

# Show the result
cv.imshow('SURF Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

---

### Advantages of SURF:
- Faster than SIFT.
- Works well under scale, rotation, and lighting variations.

### Disadvantages:
- Still slower than modern algorithms like ORB.
- Patented, which limits its use in commercial applications. 

In simple terms, SURF is a faster alternative to SIFT for finding and matching key points in images, making it great for tasks like object recognition and image alignment.

# FAST (Features from Accelerated Segment Test)
**FAST (Features from Accelerated Segment Test)** is a simple and fast algorithm used in **Digital Image Processing** to detect keypoints or corners in images. It is designed to work quickly, making it suitable for real-time applications like video processing.

---

### Key Points of FAST:

1. **Detects Corners**:
   - FAST identifies corners (keypoints) in an image by checking the intensity of pixels in a circular neighborhood around a candidate point.

2. **Fast and Efficient**:
   - The algorithm is optimized to run very quickly, even on large images, making it ideal for real-time tasks.

3. **Not Scale-Invariant**:
   - FAST works well for images of the same scale but does not automatically handle changes in size (scale).

4. **Not Rotation-Invariant**:
   - FAST does not adjust to rotated images unless combined with other methods.

---

### How FAST Works:

1. **Select a Candidate Pixel**:
   - A pixel is chosen as a candidate for being a corner.

2. **Examine Surrounding Pixels**:
   - A circle of 16 pixels around the candidate is checked.
   - If a certain number of these pixels are either significantly brighter or darker than the candidate, it is marked as a corner.

3. **Thresholding**:
   - A threshold value determines how much brighter or darker the surrounding pixels need to be compared to the candidate.

4. **Non-Maximum Suppression**:
   - To ensure accuracy, only the strongest corners in a small neighborhood are kept.

---

### Applications of FAST:

- **Object Tracking**:
   Track objects or features in video frames quickly.

- **Image Matching**:
   Detect corners to match similar areas in different images.

- **Robotics**:
   Help robots recognize and navigate their environment in real time.

---

### Example in OpenCV:

```python
import cv2 as cv

# Load the image
img = cv.imread('example.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the FAST detector
fast = cv.FastFeatureDetector_create()

# Detect keypoints
keypoints = fast.detect(img, None)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None, color=(255, 0, 0))

# Show the result
cv.imshow('FAST Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

---

### Advantages of FAST:
- Extremely fast, suitable for real-time applications.
- Easy to implement and understand.

### Disadvantages:
- Not scale or rotation invariant.
- Detects many features, which may need filtering.

In simple terms, **FAST** is a quick way to find corners or keypoints in an image, perfect for tasks where speed is more important than accuracy with scale or rotation.

# **BRIEF (Binary Robust Independent Elementary Features)**

**BRIEF (Binary Robust Independent Elementary Features)** is a method used in **Digital Image Processing** to describe keypoints in an image. Instead of using complex descriptors, BRIEF creates a simple, compact, and efficient binary string that summarizes the local appearance around a keypoint. It is fast and works well in real-time applications.

---

### Key Points of BRIEF:

1. **Describes Keypoints**:
   - BRIEF doesn't detect keypoints itself but creates a description for them based on their local neighborhood.

2. **Binary Descriptor**:
   - It generates a binary string (a sequence of 0s and 1s) by comparing the intensity of pixel pairs around the keypoint.

3. **Fast and Lightweight**:
   - BRIEF is very fast because it avoids complex computations and produces a compact descriptor.

4. **Not Scale or Rotation-Invariant**:
   - BRIEF works best when images are not rotated or scaled, but it is still robust to noise and small transformations.

---

### How BRIEF Works:

1. **Choose Keypoints**:
   - Keypoints are detected using other algorithms like FAST, SIFT, or SURF.

2. **Select a Patch**:
   - A small square region (patch) is taken around each keypoint.

3. **Compare Pixel Intensities**:
   - Pairs of pixels in the patch are selected randomly or based on a predefined pattern.
   - For each pair, check if one pixel is brighter than the other:
     - If true, output `1`.
     - If false, output `0`.

4. **Generate Descriptor**:
   - The results of the comparisons are combined into a binary string that represents the keypoint.

---

### Applications of BRIEF:

- **Feature Matching**:
   - Match features between images by comparing their binary descriptors.

- **Object Recognition**:
   - Identify objects in images based on their features.

- **Real-Time Applications**:
   - BRIEF's speed makes it ideal for tasks like video processing and robotics.

---

### Example in OpenCV:

```python
import cv2 as cv

# Load the image
img = cv.imread('example.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the FAST detector to find keypoints
fast = cv.FastFeatureDetector_create()
keypoints = fast.detect(img, None)

# Initialize the BRIEF extractor
brief = cv.xfeatures2d.BriefDescriptorExtractor_create()

# Compute descriptors
keypoints, descriptors = brief.compute(img, keypoints)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None, color=(255, 0, 0))

# Show the result
cv.imshow('BRIEF Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

---

### Advantages of BRIEF:
- Very fast and memory-efficient.
- Works well in real-time applications.

### Disadvantages:
- Not invariant to rotation or scaling.
- Needs keypoints detected by other algorithms.

In simple terms, **BRIEF** creates a quick and compact "fingerprint" for keypoints in an image, making it easy to compare and match them between images.

# **ORB (Oriented FAST and Rotated BRIEF) Overview**

**ORB (Oriented FAST and Rotated BRIEF)** is a feature detection and description algorithm used in **Digital Image Processing**. It is designed to identify and describe keypoints in images efficiently and is known for being **fast**, **accurate**, and **free to use** (open-source). ORB is a combination of two techniques: **FAST** (for detecting keypoints) and **BRIEF** (for describing them), with improvements to handle rotation and scale changes.

---

### Key Points of ORB:

1. **Fast and Lightweight**:
   - ORB is faster than algorithms like SIFT and SURF, making it ideal for real-time applications.

2. **Rotation and Scale-Invariant**:
   - It can detect and describe features even if the object is rotated or resized in the image.

3. **Free and Open-Source**:
   - Unlike SIFT and SURF, which are patented, ORB is completely free to use.

4. **Efficient Matching**:
   - ORB uses binary descriptors, making feature matching fast and memory-efficient.

---

### How ORB Works:

1. **Keypoint Detection (FAST)**:
   - ORB uses the FAST algorithm to quickly detect keypoints, which are areas in the image with strong intensity changes.

2. **Keypoint Orientation**:
   - To make the algorithm rotation-invariant, ORB assigns an orientation to each keypoint based on the intensity gradient around it.

3. **Keypoint Description (BRIEF)**:
   - ORB uses an improved version of the BRIEF descriptor to describe the detected keypoints in a compact binary format.

4. **Feature Matching**:
   - ORB matches features between images using Hamming distance, which compares binary descriptors efficiently.

---

### Applications of ORB:

- **Object Detection**:
   Recognize objects in images quickly and reliably.
   
- **Image Matching**:
   Compare and align images, such as in panorama stitching.

- **Tracking**:
   Track objects or features across video frames.

---

### Example in OpenCV:

```python
import cv2 as cv

# Load the image
img = cv.imread('example.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the ORB detector
orb = cv.ORB_create()

# Detect keypoints and compute descriptors
keypoints, descriptors = orb.detectAndCompute(img, None)

# Draw the keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None, flags=cv.DRAW_MATCHES_FLAGS_DRAW_RICH_KEYPOINTS)

# Show the result
cv.imshow('ORB Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

---

### Advantages of ORB:
- Fast and efficient, ideal for real-time applications.
- Free and open-source, suitable for both academic and commercial use.
- Works well for tasks that need scale and rotation invariance.

### Disadvantages:
- Less accurate than SIFT or SURF in some cases.
- Sensitive to large lighting changes.

In simple terms, ORB is a quick and free way to find and match important points in images, making it perfect for tasks like recognizing objects, creating panoramas, or tracking objects in videos.

# Basics of Brute-Force Matcher

**Feature Matching in OpenCV**

Feature matching is a technique used to identify similar regions between two images by comparing their keypoints and descriptors. OpenCV provides two primary methods for feature matching: Brute-Force Matching and FLANN-based Matching. 

**Brute-Force Matching:**

The Brute-Force matcher compares each descriptor from the first image with all descriptors in the second image to find the closest match based on a chosen distance metric. For example, when using ORB descriptors, the Hamming distance is commonly used.

*Example with ORB Descriptors:*

```python
import numpy as np
import cv2 as cv
import matplotlib.pyplot as plt

# Load images in grayscale
img1 = cv.imread('box.png', cv.IMREAD_GRAYSCALE)  # Query image
img2 = cv.imread('box_in_scene.png', cv.IMREAD_GRAYSCALE)  # Train image

# Initialize ORB detector
orb = cv.ORB_create()

# Detect keypoints and compute descriptors
kp1, des1 = orb.detectAndCompute(img1, None)
kp2, des2 = orb.detectAndCompute(img2, None)

# Create BFMatcher object with Hamming distance
bf = cv.BFMatcher(cv.NORM_HAMMING, crossCheck=True)

# Match descriptors
matches = bf.match(des1, des2)

# Sort matches based on distance
matches = sorted(matches, key=lambda x: x.distance)

# Draw top 10 matches
img3 = cv.drawMatches(img1, kp1, img2, kp2, matches[:10], None, flags=cv.DrawMatchesFlags_NOT_DRAW_SINGLE_POINTS)

# Display the result
plt.imshow(img3)
plt.show()
```

In this script, ORB is used to detect keypoints and compute descriptors for both images. The `BFMatcher` with Hamming distance matches these descriptors, and the top matches are visualized.

**FLANN-based Matching:**

FLANN (Fast Library for Approximate Nearest Neighbors) is more efficient for large datasets. It uses tree-based search algorithms to find the best matches.

*Example with SIFT Descriptors:*

```python
import numpy as np
import cv2 as cv
import matplotlib.pyplot as plt

# Load images in grayscale
img1 = cv.imread('box.png', cv.IMREAD_GRAYSCALE)  # Query image
img2 = cv.imread('box_in_scene.png', cv.IMREAD_GRAYSCALE)  # Train image

# Initialize SIFT detector
sift = cv.SIFT_create()

# Detect keypoints and compute descriptors
kp1, des1 = sift.detectAndCompute(img1, None)
kp2, des2 = sift.detectAndCompute(img2, None)

# Define FLANN parameters
FLANN_INDEX_KDTREE = 1
index_params = dict(algorithm=FLANN_INDEX_KDTREE, trees=5)
search_params = dict(checks=50)

# Create FLANN matcher
flann = cv.FlannBasedMatcher(index_params, search_params)

# Match descriptors using KNN
matches = flann.knnMatch(des1, des2, k=2)

# Apply ratio test to filter good matches
good_matches = []
for m, n in matches:
    if m.distance < 0.7 * n.distance:
        good_matches.append(m)

# Draw matches
img3 = cv.drawMatches(img1, kp1, img2, kp2, good_matches, None, flags=cv.DrawMatchesFlags_NOT_DRAW_SINGLE_POINTS)

# Display the result
plt.imshow(img3)
plt.show()
```

Here, SIFT is used for keypoint detection and descriptor computation. The `FlannBasedMatcher` performs KNN matching, and the ratio test filters out poor matches.

For a more detailed explanation and additional information, refer to the official OpenCV documentation. 

# Feature Matching and Homography in OpenCV

This tutorial demonstrates how to identify a known object within a complex image using feature matching combined with homography. 

**Key Steps:**

1. **Feature Detection and Description:**
   - Detect keypoints and compute descriptors in both the reference image (object) and the target image (scene) using the SIFT algorithm.

2. **Feature Matching:**
   - Utilize the FLANN-based matcher to find correspondences between descriptors from both images.

3. **Homography Calculation:**
   - If a sufficient number of good matches are found, extract the matched keypoint locations.
   - Use `cv.findHomography()` with RANSAC to compute the perspective transformation matrix (homography) between the matched points.

4. **Object Localization:**
   - Apply the homography matrix to the corners of the reference image to determine the corresponding location in the target image.
   - Draw a polygon around the detected object in the target image to visualize the match.

**Example Code:**

```python
import numpy as np
import cv2 as cv
from matplotlib import pyplot as plt

# Load images
img1 = cv.imread('box.png', cv.IMREAD_GRAYSCALE)  # Reference image
img2 = cv.imread('box_in_scene.png', cv.IMREAD_GRAYSCALE)  # Target image

# Initialize SIFT detector
sift = cv.SIFT_create()

# Detect keypoints and compute descriptors
kp1, des1 = sift.detectAndCompute(img1, None)
kp2, des2 = sift.detectAndCompute(img2, None)

# FLANN parameters
FLANN_INDEX_KDTREE = 1
index_params = dict(algorithm=FLANN_INDEX_KDTREE, trees=5)
search_params = dict(checks=50)

# Initialize FLANN-based matcher
flann = cv.FlannBasedMatcher(index_params, search_params)

# Match descriptors using KNN
matches = flann.knnMatch(des1, des2, k=2)

# Apply ratio test to find good matches
good_matches = []
for m, n in matches:
    if m.distance < 0.7 * n.distance:
        good_matches.append(m)

# Minimum number of matches required
MIN_MATCH_COUNT = 10

if len(good_matches) > MIN_MATCH_COUNT:
    # Extract location of good matches
    src_pts = np.float32([kp1[m.queryIdx].pt for m in good_matches]).reshape(-1, 1, 2)
    dst_pts = np.float32([kp2[m.trainIdx].pt for m in good_matches]).reshape(-1, 1, 2)

    # Compute homography
    M, mask = cv.findHomography(src_pts, dst_pts, cv.RANSAC, 5.0)
    matchesMask = mask.ravel().tolist()

    # Get dimensions of the reference image
    h, w = img1.shape

    # Define points to draw the bounding box
    pts = np.float32([[0, 0], [0, h - 1], [w - 1, h - 1], [w - 1, 0]]).reshape(-1, 1, 2)

    # Apply perspective transform to get bounding box in target image
    dst = cv.perspectiveTransform(pts, M)

    # Draw bounding box in target image
    img2 = cv.polylines(img2, [np.int32(dst)], True, 255, 3, cv.LINE_AA)
else:
    print(f"Not enough matches are found - {len(good_matches)}/{MIN_MATCH_COUNT}")
    matchesMask = None

# Draw matches
draw_params = dict(matchColor=(0, 255, 0),  # Matches in green
                   singlePointColor=None,
                   matchesMask=matchesMask,  # Draw only inliers
                   flags=2)

result_img = cv.drawMatches(img1, kp1, img2, kp2, good_matches, None, **draw_params)

# Display result
plt.imshow(result_img, 'gray')
plt.show()
```

This script detects keypoints in both images, matches them, computes the homography to map the reference image onto the target image, and draws the detected object within the scene.

For a comprehensive understanding and additional details, refer to the official OpenCV documentation. 

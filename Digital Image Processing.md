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

**Introduction to SIFT (Scale-Invariant Feature Transform)**

SIFT is a method used in computer vision to detect and describe local features in images. It identifies key points that are invariant to scale and rotation, making it effective for object recognition and image matching. 

**Key Concepts:**

1. **Scale-Space Extrema Detection:**
   - Detects potential key points by identifying local maxima and minima in the Difference of Gaussians (DoG) across various scales.

2. **Keypoint Localization:**
   - Refines the detected key points by eliminating those with low contrast or that are poorly localized along edges.

3. **Orientation Assignment:**
   - Assigns a consistent orientation to each key point based on local image gradient directions, ensuring invariance to image rotation.

4. **Keypoint Descriptor:**
   - Generates a descriptor for each key point by computing the local image gradients around the key point, which is then used for matching purposes.

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

For a more detailed explanation and additional information, refer to the official OpenCV documentation. 

**Introduction to SURF (Speeded-Up Robust Features)**

SURF is a method in computer vision used to detect and describe key points in images. It's designed to be faster than the earlier SIFT algorithm while maintaining similar performance. 

**Key Features of SURF:**

- **Speed:** SURF uses box filters to approximate the Laplacian of Gaussian, allowing for quick computations with integral images.

- **Key Point Detection:** It identifies key points using the determinant of the Hessian matrix, ensuring both scale and location invariance.

- **Orientation Assignment:** SURF calculates the dominant orientation around each key point using wavelet responses, making the features rotation-invariant. For applications where rotation invariance isn't needed, Upright-SURF (U-SURF) can be used for faster processing.

- **Descriptor Size:** The standard SURF descriptor is 64-dimensional, but there's an extended 128-dimensional version for increased feature distinctiveness.

- **Sign of Laplacian:** SURF uses the sign of the Laplacian to distinguish between bright blobs on dark backgrounds and vice versa, aiding in faster feature matching.

**Using SURF in OpenCV:**

OpenCV provides tools to work with SURF. You can create a SURF object, adjust parameters like the Hessian threshold, and detect key points and descriptors.

**Example Code:**

```python
import cv2 as cv

# Load the image in grayscale
img = cv.imread('fly.png', cv.IMREAD_GRAYSCALE)

# Create SURF object with Hessian Threshold set to 400
surf = cv.xfeatures2d.SURF_create(400)

# Detect keypoints and compute descriptors
kp, des = surf.detectAndCompute(img, None)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, kp, None, (255, 0, 0), 4)

# Display the result
cv.imshow('SURF Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

This script loads an image, converts it to grayscale, detects SURF key points and computes their descriptors, draws the key points on the original image, and displays the result.

For a comprehensive understanding and additional details, refer to the official OpenCV documentation. 

**FAST Algorithm for Corner Detection**

The FAST (Features from Accelerated Segment Test) algorithm is a method used in computer vision to detect corners in images quickly. It was introduced by Edward Rosten and Tom Drummond in their 2006 paper, "Machine learning for high-speed corner detection." 

**Key Concepts:**

1. **Corner Detection:**
   - FAST identifies a pixel as a corner if there exists a set of contiguous pixels in a circular neighborhood that are all significantly brighter or darker than the central pixel.

2. **High-Speed Test:**
   - To improve efficiency, FAST first examines four specific pixels in the circle. If these pixels are not all brighter or darker, the algorithm quickly discards the point as a corner candidate.

3. **Machine Learning Enhancement:**
   - A decision tree classifier is trained to optimize the order of pixel examinations, further speeding up the detection process.

4. **Non-Maximal Suppression:**
   - To ensure that only the most prominent corners are detected, FAST applies non-maximal suppression, which retains the strongest corner responses and eliminates weaker, adjacent ones.

**Implementation in OpenCV:**

OpenCV provides an implementation of the FAST algorithm through the `cv2.FastFeatureDetector_create()` function. Users can adjust parameters such as the threshold value and whether to apply non-maximum suppression.

**Example Code:**

```python
import cv2 as cv
import numpy as np

# Load the image in grayscale
img = cv.imread('blox.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the FAST detector
fast = cv.FastFeatureDetector_create()

# Detect keypoints
keypoints = fast.detect(img, None)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, keypoints, None, color=(255, 0, 0))

# Display the result
cv.imshow('FAST Keypoints', img_with_keypoints)
cv.waitKey(0)
cv.destroyAllWindows()
```

This script loads a grayscale image, detects keypoints using the FAST algorithm, draws these keypoints on the image, and displays the result.

For a more detailed explanation and additional information, refer to the official OpenCV documentation. 

**BRIEF (Binary Robust Independent Elementary Features)**

BRIEF is a feature descriptor in computer vision that efficiently describes keypoints using binary strings, making it faster and more memory-efficient compared to descriptors like SIFT and SURF. 

**Key Points:**

- **Descriptor Generation:** BRIEF computes a binary string for each keypoint by comparing the intensities of specific pixel pairs within a smoothed image patch. If the intensity at one pixel is less than the other in the pair, the result is 1; otherwise, it's 0. This process is repeated for a set number of pixel pairs to form the descriptor.

- **Advantages:** BRIEF descriptors are compact and can be matched quickly using Hamming distance, which involves simple XOR operations and bit counting. This efficiency makes BRIEF particularly useful for applications where speed and memory are critical. However, BRIEF is sensitive to in-plane rotations; its performance may degrade with significant image rotations.

**Implementing BRIEF in OpenCV:**

To use BRIEF in OpenCV, you need to detect keypoints using a detector like STAR (derived from CenSurE) and then compute the BRIEF descriptors for these keypoints.

**Example Code:**

```python
import cv2 as cv
import matplotlib.pyplot as plt

# Load the image in grayscale
img = cv.imread('simple.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the STAR detector
star = cv.xfeatures2d.StarDetector_create()

# Initialize the BRIEF extractor
brief = cv.xfeatures2d.BriefDescriptorExtractor_create()

# Detect keypoints using STAR
kp = star.detect(img, None)

# Compute BRIEF descriptors for the keypoints
kp, des = brief.compute(img, kp)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, kp, None, color=(255, 0, 0))

# Display the result
plt.imshow(img_with_keypoints)
plt.show()
```

In this script, we load a grayscale image, detect keypoints using the STAR detector, compute their BRIEF descriptors, and visualize the keypoints on the image.

For more detailed information, refer to the official OpenCV documentation. 

**ORB (Oriented FAST and Rotated BRIEF) Overview**

ORB is a feature detection and description algorithm in computer vision that combines the FAST keypoint detector and the BRIEF descriptor, with enhancements for improved performance. It offers an efficient alternative to algorithms like SIFT and SURF, especially in terms of computational cost and patent restrictions. 

**Key Features of ORB:**

- **Keypoint Detection:** ORB utilizes the FAST algorithm to detect keypoints and applies the Harris corner measure to select the top N points, ensuring robust feature detection across multiple scales using image pyramids.

- **Orientation Assignment:** To achieve rotation invariance, ORB computes the intensity-weighted centroid of the detected keypoint's neighborhood. The vector from the keypoint to this centroid determines the orientation, allowing the algorithm to handle rotated images effectively.

- **Descriptor Computation:** While BRIEF descriptors are not inherently rotation-invariant, ORB addresses this by "steering" the BRIEF descriptors according to the keypoint's orientation. This adjustment ensures that the descriptors remain consistent even when the image undergoes rotation.

- **Descriptor Optimization:** ORB selects binary tests that exhibit high variance and means close to 0.5, ensuring that each bit in the descriptor is both discriminative and uncorrelated. This process results in the rBRIEF descriptor, which enhances matching performance.

**Implementing ORB in OpenCV:**

OpenCV provides an easy-to-use interface for ORB through the `cv.ORB_create()` function. Users can adjust parameters such as the number of features (`nFeatures`), the score type (`scoreType`), and the number of points for each element of the descriptor (`WTA_K`).

**Example Code:**

```python
import cv2 as cv
import matplotlib.pyplot as plt

# Load the image in grayscale
img = cv.imread('simple.jpg', cv.IMREAD_GRAYSCALE)

# Initialize the ORB detector
orb = cv.ORB_create()

# Detect keypoints
kp = orb.detect(img, None)

# Compute descriptors
kp, des = orb.compute(img, kp)

# Draw keypoints on the image
img_with_keypoints = cv.drawKeypoints(img, kp, None, color=(0, 255, 0), flags=0)

# Display the result
plt.imshow(img_with_keypoints)
plt.show()
```

This script loads a grayscale image, detects keypoints using ORB, computes their descriptors, and visualizes the keypoints on the image.

For a comprehensive understanding and additional details, refer to the official OpenCV documentation. 

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

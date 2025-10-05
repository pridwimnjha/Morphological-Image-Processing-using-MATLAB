# 🧠 Morphological Image Processing using MATLAB

![MATLAB](https://img.shields.io/badge/MATLAB-R2023b-blue?logo=mathworks)
![Image Processing](https://img.shields.io/badge/Image%20Processing-Morphological%20Operations-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📘 Project Overview

This MATLAB project demonstrates the **fundamental morphological operations** — **dilation**, **erosion**, **opening**, and **closing** — applied to a grayscale image using **different structuring elements** such as *square*, *circle (disk)*, *diamond*, and *disc*.

Morphological operations are widely used in **image preprocessing**, **noise removal**, **object detection**, and **feature extraction** in image processing.

---

## 🧩 Key Concepts

1. **Dilation** – Expands the bright regions (foreground) of the image.
2. **Erosion** – Shrinks or thins the bright regions of the image.
3. **Opening** – Erosion followed by dilation, useful for removing small noise.
4. **Closing** – Dilation followed by erosion, useful for filling small holes.

Each operation is performed using four structuring elements:

* 🟦 Square (`strel('square', 10)`)
* ⚪ Circle (`strel('disk', 10)`)
* 🔷 Diamond (`strel('diamond', 10)`)
* 🌀 Disc (`strel('disk', 10)`)

---

## 🧮 MATLAB Code

```matlab
a = imread("EXP_6_IMG.jpeg");
b = rgb2gray(a);

square = strel('square', 10);
circle = strel('disk', 10);
diamond = strel('diamond', 10);
disc = strel('disk', 10);

% Dilation
c1 = imdilate(b, square);
c2 = imdilate(b, circle);
c3 = imdilate(b, diamond);
c4 = imdilate(b, disc);

% Erosion
d1 = imerode(b, square);
d2 = imerode(b, circle);
d3 = imerode(b, diamond);
d4 = imerode(b, disc);

% Opening
e1 = imopen(b, square);
e2 = imopen(b, circle);
e3 = imopen(b, diamond);
e4 = imopen(b, disc);

% Closing
f1 = imclose(b, square);
f2 = imclose(b, circle);
f3 = imclose(b, diamond);
f4 = imclose(b, disc);

% Display results
figure;
subplot(2,2,1), imshow(c1), title('Dilation - Square');
subplot(2,2,2), imshow(c2), title('Dilation - Circle');
subplot(2,2,3), imshow(c3), title('Dilation - Diamond');
subplot(2,2,4), imshow(c4), title('Dilation - Disc');

figure;
subplot(2,2,1), imshow(d1), title('Erosion - Square');
subplot(2,2,2), imshow(d2), title('Erosion - Circle');
subplot(2,2,3), imshow(d3), title('Erosion - Diamond');
subplot(2,2,4), imshow(d4), title('Erosion - Disc');

figure;
subplot(2,2,1), imshow(e1), title('Opening - Square');
subplot(2,2,2), imshow(e2), title('Opening - Circle');
subplot(2,2,3), imshow(e3), title('Opening - Diamond');
subplot(2,2,4), imshow(e4), title('Opening - Disc');

figure;
subplot(2,2,1), imshow(f1), title('Closing - Square');
subplot(2,2,2), imshow(f2), title('Closing - Circle');
subplot(2,2,3), imshow(f3), title('Closing - Diamond');
subplot(2,2,4), imshow(f4), title('Closing - Disc');
```

---

## 🖼️ Output

The program displays **four figures**, each showing the effect of different morphological operations using various structuring elements:

1. **Dilation Results**
2. **Erosion Results**
3. **Opening Results**
4. **Closing Results**

Each figure is divided into 2×2 subplots representing:

* Square
* Circle
* Diamond
* Disc

---

## 📊 Applications

* Image Preprocessing for Machine Learning
* Edge and Shape Detection
* Object Segmentation
* Noise Filtering and Image Restoration

---

## 📚 References

* MathWorks Documentation: [Morphological Operations](https://www.mathworks.com/help/images/morphological-dilation-and-erosion.html)
* Gonzalez & Woods, *Digital Image Processing*, 4th Edition.

---

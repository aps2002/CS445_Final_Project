# CS445_Final_Project :camera_flash:

We have developed a software that takes two people's faces and morphs the first person's face into the second person's face :bangbang: We did this for our final project for CS 445: Computational Photography :computer: offered by the University of Illinois at Urbana-Champaign :school:.

## Our Motivation :smile:

We chose this topic at the beginning because we found the concept of Image morphing very interesting since we have actually seen it in youtube videos and apps. These platforms show a very cool transition between 2 faces and it seems interesting to research this due to the interesting math :heavy_multiplication_x: and linear algebra involved in this progress. We will learn :brain: more in depth about image transformation, specifically the laplacian transform and the fast fourier transform, since we will need to consider high and low frequency components in our project.

## How It Works :thinking:
There are 5️⃣ important concepts to understanding face morphing:

### 0️⃣ Detecting at least one face in both images:

We use dlib, a modern C++ toolkit :toolbox: containing machine learning algorithms, to make sure we can find the faces 🤠 in both images. This wouldn't work if there were no faces in the images!

### 1️⃣ Detecting facial landmarks on both faces:

At this point, we know there are faces, but we don't know anything about them. We want to look for the person's facial features, like their eyebrows 🤨, eyes 👁️, where their cheeks end, their mouth 😮, nose 👃, and chin. By knowing 🧠 this information, we know which areas of the images 🖼️ we need to focus in. Again, we use dlib to find these points. We grab 68 different coordinates for each face. These get stored in a list in ```[(x1,y1),(x2,y2),...]``` format.

### 2️⃣ Find Delaunay Triangulation 🔺 🔻
We now know where all of our facial features are for both images, but now we find the delaunay triangulation 📐. From each of our 68 points, we draw triangles from one point to the next closest one 📏. Delaunay Triangulation is used to transform one face to another, and also help with facial geometry. The diagram below first shows all 68 points plotted onto President Obama's face. The middle image 🖼️ shows Delaunay Triangulation performed on all 6️⃣8️⃣ points.

![Visual of Delaunay Triangulation](https://learnopencv.com/wp-content/uploads/2015/11/opencv-delaunay-vornoi-subdiv-example.jpg)

Image taken from learnopencv.com

### 3️⃣ Warping Triangular Mesh

### 4️⃣ Reconstruct Faces

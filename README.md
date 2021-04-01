# Maze-solver
--> **sovling mazes in efficient way in python using Dijkstra’s Algorithm**
-->using  OpenCV, a popular computer vision library for Python, to extract pixel values and show our maze images
-->We can think of an image as a matrix of pixels. Each pixel (for simplicity’s sake) has an RGB value of 0,0,0 (black) or 255,255,255 (white). Our goal is to create a shortest path which starts in the white and does not cross into the black boundaries. To represent this goal we can treat each pixel as a node and draw edges between neighboring pixels with edge lengths based on RGB value differences. We will use the Euclidean squared distance formula and add 0.1 to ensure no 0-distance path lengths (a requirement for Dijkstra’s algorithm):


-->This formula makes the distance of crossing through the maze boundary prohibitively large. As we can see, the shortest path from source to destination will clearly be around the barrier, not through it.
![Alt Text](https://miro.medium.com/max/741/1*Xccrpgo6hokbvtO3qcUYRw.png)

#**implementation:**
We can use OpenCV, a popular computer vision library for Python, to extract pixel values and show our maze images. Let’s also identify the coordinates of our starting and ending locations by adding points to our maze

2>We create a Vertex class which will help us keep track of the coordinates. We also want to keep track of the parent node so that we can reconstruct the entire path once we find our distance values.

3>We need to create a matrix of Vertices, representing the 2D layout of pixels in an image. This will be the basis for our Dijkstra’s algorithm graph. We also maintain a min-heap priority queue to keep track of unprocessed nodes.

4>We need several helper functions to help find edges and edge lengths between vertices:

5>Now, we can implement Dijkstra’s Algorithm and assign distance (d) values to all of the pixel Vertices in the maze image:

6>We can now call our shortest path function and draw the solution on our maze:

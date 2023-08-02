# StarDataCapture: 
## A Novel Method for Analyzing Images in Space

## Background
StarDataCapture is a resource that collects and organizes data from any .fits image of space. It can identify stars
and print the characteristics of every star.
There are currently no fullproof star identification programs but during this project I coded and tested two
formats. The first one identified stars purely based on pixel brightness. This caused multiple issues because
stars would be counted multiple times. My final design identifies stars based on the ratio of the contrast between
the star and the background, and by shape. We began coding wit the contrast by creating a aperture that would
loop through the image in squares. To improve this the square was turned into a circle, this way we got a more
accurate count over the star.
Even large code that people work for years on can have limitations. This, that was done in a month does too.
Given more time I could’ve found ways to work out the little tweaks. This program isn’t great at identifying dim
stars, or stars that are close together, and sometimes it gets confused when there are other subjects in the image.
Though there are slight ways to get better results, it will never be perfect.
In the main image I used to create this code, there were 3 stars that I was never able to get the computer to 
properly identify. But in the end, it was able to produce sufficient results.

## Instructions
To use the StarDataCapture code, you will want to copy and paste the code into a code editor. Once you have it,
there are instructions throughout the code to run the code through your .fits image properly.

## Results
After running the code through your image, you should be left with a list with the coordinates, the average
brightness of the star located, the average brightness of the background around it, and the ratio between them for
each star. There will also be a plot with all of the points on top of your original image.(Since this program has to run through every pixel in the image, it takes a few minutes to produce the data)


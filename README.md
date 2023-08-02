# StarDataCapture: 
## A Novel Method for Analyzing Images in Space

## Background
StarDataCapture is a resource that collects and organizes data from any .fits image of space. It can identify stars
and return the data of every star.
There are currently no fullproof star identification programs but during this project I coded and tested multiple
formats. The first one identified stars purely based on pixel brightness. This caused multiple issues because
stars would be counted multiple times and would often confuse other objects as stars. Then began my work into the final code. I began by using the difference in brightness between the star and background, but I soon found this was not usefull when apply the code to other images. My final design identifies stars based on the ratio of the contrast between the star and the background, and by shape. I used the contrast to identify by creating a aperture that would
loop through the image in squares. This aperture would find the average brightness of the pixels in the star and of the background and compute the ratio between them. To improve this the square was turned into a circle, now the count over the star would be more accuratly shaped and include less background within the star.

Even large code that people work on for years can have limitations. This program, that was done in a month does too.
Given more time I could’ve found ways to work out the little tweaks. This program isn’t great at identifying dim
stars, or stars that are close together, and sometimes it gets confused when there are other subjects in the image.
Though there are slight ways to get better results, it will never be perfect. These problems occur because the computer does not see the image as we do, it is scanning over an array of values, we must be the ones that tell it what to do with the information. 
In the main image I used to create this code, there were 3 stars that I was never able to get the computer to 
properly identify. But in the end, it was able to produce sufficient results.

In the future I would hope to fix some of these complications. I think if I could specify the brightess ratio better(possibly with a range) and the shape of the stars better it would improve many features. With this, it would rarely get false positive stars

## Instructions
To use the StarDataCapture code, you will want to copy and paste the code into a code editor. Once you have it,
there are instructions throughout the code to run the code through your .fits image properly.

## How it Works
StarDataCapture works by running an aperture over every pixel to search for stars. As it goes over the image it is looking for circular shapes that have a set brightness ratio between the star itself and the background. Then, it must be able to distinguish which pixels correspond to which stars and be aware that a star should not be counted more than once. If it encounters a "star" that is within a set radius of another star, it will not count it. 

Because of the diversity of space imaging, you must input some data manually. This makes the code more accesible.
This is especially necessary when it comes to the size of the stars, these vary drastically depending on the image so I found it produced more accurate results this way. You must also input the brightness ratio and distance between stars, these are just formalities that help the code understand your image.

## Results
After running the code through your image, you should be left with a list with the coordinates, the average
brightness of the star located, the average brightness of the background around it, and the ratio between them for
each star. There will also be a plot with all of the points on top of your original image.(Since this program has to run through every pixel in the image, it takes a few minutes to produce the data)


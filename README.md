# StarDataCapture: 
## A Novel Method for Analyzing Images in Space

## Background
StarDataCapture is a resource that collects and organizes data from any .fits image of space. It can identify stars
and return the coordinates, star brightness, background brightness, and brightness ratio for every star.
There are currently no fullproof star identification programs but during this project I coded and tested multiple
formats. The first one identified stars purely based on pixel brightness. This caused multiple issues because
stars would be counted multiple times and would often confuse other objects as stars. Then began my work into the final code. I began by using the difference in brightness between the star and background, but I soon found this was not usefull when apply the code to other images. My final design identifies stars based on the ratio of the contrast between the star and the background, and by shape. I used the contrast to identify by creating a aperture that would
loop through the image in squares. This aperture would find the average brightness of the pixels in the star and of the background and compute the ratio between them. To improve this the square was turned into a circle, now the count over the star would be more accuratly shaped and include less background within the star.

Even large code that people work on for years can have limitations. This program, that was done in a month does too.
Given more time I could’ve found ways to work out the little tweaks. This program isn’t great at identifying dim
stars, or stars that are close together, and sometimes it gets confused when there are other subjects in the image.
Though there are slight ways to get better results, it will never be perfect. These problems occur because the computer does not see the image as we do, it is scanning over an array of values, we must be the ones that tell it what to do with the information. 
In the main image I used to create this code, there were 3 stars that I was never able to get the computer to 
properly identify. Those stars were larger than others so the background brightness included parts of the stars and were not calculated properly. In the end, we were able to recieve sufficient results. There were no visible false positives and the three stars were the only false negatives.

In the future I would hope to fix some of these complications. I think if I could specify the brightess ratio better(possibly with a range) and the shape of the stars better it would improve many features. With this, it would rarely mis-calculate stars.

## Instructions
To use the StarDataCapture code, you will want to copy and paste the code into a code editor. Once you have it,
there are instructions throughout the code to run the code through your .fits image properly.

## How it Works
StarDataCapture works by running an aperture over every pixel to search for stars. The aperture separates the star from the background around it. This way, we can calculate both areas separtly. It loops over the image searching for areas with a set brightness ratio between the center and outer part of the aperture. When it finds an area that follows the requirements of a star, it confirms the star and moves on to the next pixel. It is likely that the following pixels will also be identified as stars. As it runs, the code checks a set radius around the point, if there are no "stars" around it then it may continue, if it does locate another "star" it is not counted. It is likely that this other "star" was just another pixel in the same star. In the code you may set your own distance radius to decide how close together your stars can be. This loop will continue through the whole image. If your image is larger the code will take much longer to run.

Because of the diversity of space imaging, you must input some data manually. This makes the code more accesible. This is especially necessary when it comes to the size of the stars, these vary drastically depending on the image so I found it produced more accurate results this way. You must also input the brightness ratio and distance between stars, these are just formalities that help the code understand your image.

## Results
After running the code through your image, you should be left with a list with the coordinates, the average
brightness of the star located, the average brightness of the background around it, and the ratio between them for
each star. There will also be a plot with all of the points on top of your original image.(Since this program has to run through every pixel in the image, it takes a few minutes to produce the data)

# Running
To run this code, you must first install jupite notebook with:
## !pip install notebook
and to run:
## jupyter notebook
to run StarDataCapture:
Click the three dots on the StarDataCapture code and download
Then go to jupyter notebook, click upload, and select StarDataCapture.ipynb

# Testing
1. Download this file, https://www.swift.ac.uk/archive/reproc/00016150001/uvot/image/sw00016150001ubb_sk.img.gz 
2. In your files, unzip the image by extracting it into your Home directory
3. Paste it in the 'fits_image_url' place
4. For the NAXIS use 1
5. in the yaxis put 826
6. in the xaxis put 927
7. for star radius put 2
8. for minimum_between_stars put 20
9. for star_background_ratio put 10

# To construct slidepresentation
1. Download slidepresentation file
2. in terminal run 'cd slidepresentation'
3. then run 'pdflatex slidepresentation'


We begin by creating a blank image. For each pixel we will do one of two things: half the time, we will simply copy the pixel from that location in the old picture. The other half of the time we will find a pixel nearby and copy that pixel instead. We will do this by generating a random number between 0 and 1. If the random number generated is less than 0.5 (which it will be approximately half the time), we will copy the pixel from the old picture. Otherwise, we will find and copy a nearby pixel.

We must figure out how to find a "nearby" pixel. We will define some value for how far away the new pixel will be (say, 10 pixels) and then we write a function that will give x and y coordinates that are a random amount between 0 and 10 pixels away. For example, it could give a pixel that is 5 pixels to the left and 3 pixels higher.

Before we use these coordinates to get a new pixel, we must check that the new coordinates still give a valid pixel in the image. For example, imagine we are finding a pixel to replace a pixel at the very top of the image. The function that generates coordinates gives us a point that is 3 pixels up, but since we are on the top of the image (y = 0) we cannot go up by three pixels (y would be -3)! If the random number is too big (larger than the width-1 or height-1) or too small (less than 0) then we will just use the closest number that is valid.

Once we have a valid pixel that is some amount away, we use its red, green, and blue values as the new pixel's values.


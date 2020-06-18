# BSP - ArtisticImages
This repo is a work from college, which consists in generating an artistic image with a real image as input.
</br>
</br>
This repository is public in order to show the solution to the problem, __but it must not be reworked, copied, used, downloaded, disclosed or any other purpose.__ This repository is for the __private and exclusive__ use of students in the discipline of Basic Software Program of class 127 - 2020/1 of the Software Engineering course at the Polytechnic School of PUCRS college. 
</br>
</br>

## Proposed problem
The objective of this work is to implement an algorithm for transforming any image into a stylized version.
The idea of this algorithm is to discover points of influence in the image, so that they identify regions affected by it. These regions are then painted with a single color.
The styling algorithm we use is a simplification of a well-known geometric algorithm, called a Voronoi diagram.

## How does it work?
An image is represented by a dot matrix (pixels), where each color is defined by 3 components: red (R), green (G) and blue (B). Each of these components is encoded in one byte, which produces 3 bytes per pixel (24 bits) - that is, 16 million possible colors. In other words, the intensities (R, G, B) vary from 0 to 255, where 0 is dark and 255 is light.
See below how different colors are represented in this format - each color is expressed by the RGB components in hexadecimal.

<img align="center" src="https://i.imgur.com/j56OBAk.png">


- A certain amount of "seeds" is chosen, that is, positions of influence within the image. This choice can be purely random or employ some other more sophisticated technique. Each seed has a position (xsi, ysi), and a color representative of that region (see below).
- For each pixel of the input image (x, y), the closest seed is found, that is, the one whose distance is the shortest to it. To calculate the distance, you can use the Euclidean distance formula:

```
dist= √((x−xs)²+(y−ys)²)
```

- In the output image, the color representative of the region in the current pixel is then stored.
- The process continues until the algorithm passes through all the pixels in the original image (usually from left to right and top to bottom).


## Image code example
Below is an example of the styling process carried out by the implemented algorithm. It is worth mentioning that the process is not done in steps, as the image shown. 
The only result obtained by the code is that of the last image.

![Stylization process using the implemented algorithm.](https://mflash.github.io/progswb2/trab/t1-201-jhhe4udhv7/muitasfacins.jpg)


By: [luizeduardomr](https://github.com/luizeduardomr) & [LucasGCardoso](https://github.com/LucasGCardoso)

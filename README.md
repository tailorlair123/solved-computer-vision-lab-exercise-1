Download Link: https://assignmentchef.com/product/solved-computer-vision-lab-exercise-1
<br>
<h1>Computer Vision Linear Filters: Gaussians and Derivatives</h1>

<h2>1        1D Gaussian Filter</h2>

In this first part, you will be implementing a 1D discrete Gaussian filter:

(1)

where <em>σ </em>is the variance of the Gaussian. The Matlab function should look like this:

<ul>

 <li>function G = gaussian( sigma )</li>

 <li>…</li>

 <li>end</li>

</ul>

<h2>2                 Convolving an image with a 2D Gaussian</h2>

You will write a function to convolve an image with a 2D Gaussian. One of the most important properties of Gaussian kernels is separability. Therefore, convolving an image with a 2D Gaussian is equivalent to convolving the image along the x-axis and the y-axis separately with a 1D Gaussian. The Matlab function should use the previous function and should look like this:

<table width="527">

 <tbody>

  <tr>

   <td width="527">1      function imOut = gaussianConv(imagepath , sigma x , sigma y)2      …3      end</td>

  </tr>

 </tbody>

</table>

Hint: use Matlab function conv2.

<h2>3                 Comparing with Matlab’s Gaussian Filter</h2>

Matlab already has a built-in function implementing 2D Gaussian kernels. The Matlab code for using it is:

<ul>

 <li>G=fspecial(‘gaussian’,n,sigma)</li>

 <li>imOut=conv2(imIn,G,’same’)</li>

</ul>

In this part, you can compare your implementation of 2D Gaussian convolution, through two 1D operations, to Matlab’s. You can read any image and check the difference between your output image and Matlab’s.

<h2>4       Gaussian Derivative</h2>

The Gaussian first order derivative is given by:

Write a function to implement this first order derivative. Your function should look like this:

<ul>

 <li>function Gd =gaussianDer(G , sigma)</li>

 <li>…</li>

 <li>end</li>

</ul>

<h2>5         Gradient Magnitude and Orientation</h2>

Write a function that returns two images with the magnitude and orientation of the gradient for each pixel of the input image. Your function should look like this:

<ul>

 <li>function [magnitude , orientation] = gradmag(img , sigma)</li>

 <li>…</li>

 <li>end</li>

</ul>

<h3>5.1</h3>

Visualize your result using:

<ul>

 <li>imshow(orientation , [-pi,pi])</li>

 <li>colormap(hsv);</li>

 <li>colorbar;</li>

</ul>

Visualize your result using Matlab quiver function.

<h3>5.2</h3>

Get results for varying sigma values.

<ol>

 <li>How do the magnitude images change as the sigma increases?</li>

 <li>How do the orientation images change as the sigma increases?</li>

</ol>

<h3>5.3</h3>

It is typical to place a threshold on the gradient magnitude so that the edge detection result is binary. Use different thresholds on the gradient magnitude and display your thresholded image for varying sigma values.

<h3>5.4</h3>

The Gaussian second order derivative is given by:

Write a function that give an output of the specified derivative of an input image (type : ’x’, ’y’, ’xx’, ’yy’, ’xy’, ’yx’). Your function should look like this:

<table width="527">

 <tbody>

  <tr>

   <td width="27">1</td>

   <td width="500">function F=ImageDerivatives(img , sigma , type)</td>

  </tr>

  <tr>

   <td width="27">2</td>

   <td width="500">…</td>

  </tr>

  <tr>

   <td width="27">3</td>

   <td width="500">end</td>

  </tr>

 </tbody>

</table>

<h3>5.5</h3>

Create an impulse image (all zeros, with only one pixel in the center set to the maximum value) and convolve the impulse image with 0, 1st, and 2nd order gaussian derivatives, try some sigma values and visualize the result images. Describe what you see. Is there a relation between the order and the sigma?
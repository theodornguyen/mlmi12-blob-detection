# Blob Detection with the Laplacian of Gaussian
In Computer Vision, blob detection is used to find characteristical image locations to compute image features. In SIFT's multi-scale blob-detection algorithm, the Laplacian of Gaussian (LoG) $\nabla^2G(x,y,\sigma)$ acts as a bandpass filter, leaving extrema at the center of the blobs. The Gaussian reduces noise in the image before the Laplacian detects regions of high-intensity change. As $\sigma$ approaches the right scale of the blob, LoG's responses converge to a maximum at the blob's center, motivating the usage of LoG for blob detection. To detect blobs at different scales, the image is blurred to different resolutions, which can be achieved by low-pass filtering the image with a Gaussian at different scales, i.e. with different variances. The variance $\sigma$ of the smoothing Gaussian is increased logarithmically from $\sigma$ to $2\sigma$ before the image is subsampled, as the blurring can be continued more efficiently in the subsampled images. This procedure of increasing the variance of the smoothing Gaussian to $2\sigma$ and subsampling is called the __image pyramid__.

We perform multiscale blob detection with an image of tulips.

![](/images/1t.png)

First, we greyscale the image.

![](/images/2t.png)

We convolve the Laplacian of Gaussian with a logarithmic scale. Plotting the results of the convolutions gives us the Gaussian-filtered images.

![](/images/3t.png)

 Thresholding the convolutions gives us the blob regions.

![](/images/4t.png)

Finally, we can plot the local maxima at their respective scale.

![](/images/5t.png)



# image-brightness-and-contrast-enhancement
Brightness and Contrast enhancement comparision using pixel and global transformations

### Pixel Level Tranformation

#### Linear Pixel Transform
Changing pixel values using, ```y = a(pixel) + b``` where a and b are often called the gain and bias parameters; sometimes these parameters are said to control contrast and brightness respectively.

#### Non-Linear Tranformation (Gamma Correction)
Non linear pixel transform done using ```O=((I/255)^gamma)×255```.
The gamma correction should tend to add less saturation effect as the mapping is non linear and there is no numerical saturation possible as in the previous method.



### Global Tranformation

#### Global Image Histogram Equalization
This method usually increases the global contrast of many images, especially when the usable data of the image is represented by close contrast values. Through this adjustment, the intensities can be better distributed on the histogram. This allows for areas of lower local contrast to gain a higher contrast. Histogram equalization accomplishes this by effectively spreading out the most frequent intensity values.

The method is useful in images with backgrounds and foregrounds that are both bright or both dark. In particular, the method can lead to better views of bone structure in x-ray images, and to better detail in photographs that are over or under-exposed. 

#### Contrast Limited Adaptive Histogram Equalization (CLAHE)
In this, image is divided into small blocks called "tiles" (tileSize is 8x8 by default). Then each of these blocks are histogram equalized as usual. So in a small area, histogram would confine to a small region (unless there is noise). If noise is there, it will be amplified. To avoid this, contrast limiting is applied. If any histogram bin is above the specified contrast limit (by default 40), those pixels are clipped and distributed uniformly to other bins before applying histogram equalization. After equalization, to remove artifacts in tile borders, bilinear interpolation is applied.

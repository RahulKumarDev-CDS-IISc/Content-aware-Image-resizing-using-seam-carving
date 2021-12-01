# Content aware Image resizing using seam carving
* * *
This is the implementation from scratch of seam carving in Image resizing and object removal.

> 1. To resize an image , we can use cropping, or scaling(distortions) . Both these methods remove essential information from the image. We intend to do resizing of an image without loosing information of ROI(Region of interest) using seam carving.
> 2. And we also want to extend idea of seam carving to object removal.

### Methodologies and results:
1. We take the image.
<img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img.png" width="350"/>
2. Performed edge detection using Sobel Operator. 
<img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_edge.png" width="350">

3. Seam :- The path of connected pixels which has minimum cost. Used DP(Dynamic Programming) for finding the seam with minimum cost.
<img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_energy.png" width="350">

4. Removal of seam with lowest cost in downscaling the image. Adding k-seam with k-lowest cost seam in upscaling the image (where k is the resultanat number of seam we have to add in upscaling the image).
<img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_original.png" width="350"> <img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_ori_energy.png" width="350"/> <img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_ori_image.png" width="350"/> <img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/img_carved.png" width="350">
5. For object removal, user will choose the region which they want to remove.
6. Then by decreasing the importance of each pixels in the selected patch, we made seams to pass through the selected patch of region which user want to remove.

<img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/obj.png" width="405"/> <img src="https://github.com/RahulKumarDev-CDS-IISc/Content-aware-Image-resizing-using-seam-carving/blob/main/images/obj_rem.png" width="350">

* * *
### Requirements
- Python 3.7 or above
- openCV
- scikit image
- matplotlib
- numpy
- scipy
- tqdm


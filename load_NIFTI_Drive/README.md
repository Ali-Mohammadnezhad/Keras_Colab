```
from google.colab import drive
drive.mount('/content/drive')
```
```
import nibabel as nib
import matplotlib.pyplot as plt
import numpy as np
# Set numpy to print only 2 decimal digits for neatness
np.set_printoptions(precision=2, suppress=True)
#..........................................................
#img = nib.load('/content/drive/MyDrive/DTI_FA/3104_dtifit_FA.nii.gz')
img1 = nib.load('/content/drive/MyDrive/DTI_FA/3104_dtifit_FA.nii.gz').get_fdata()
img2=  nib.load('/content/drive/MyDrive/DTI_FA/3104_FA_gauss.nii.gz').get_fdata()
img3=  nib.load('/content/drive/MyDrive/DTI_FA/3104_FA_median.nii.gz').get_fdata()
#img.shape
#print(type(img))
test1 = img1[:,40,:]
test2 = img2[:,40,:]
test3 = img3[:,40,:]
#plt.imshow(test)
#plt.show()

# Plot 1
plt.subplot(1, 3, 1)
plt.imshow(test1)

# Plot 2
plt.subplot(1, 3, 2)
plt.imshow(test2)

# Plot 3
plt.subplot(1, 3, 3)
plt.imshow(test3)
```
![image](https://github.com/Ali-Mohammadnezhad/Keras_Colab/assets/110347490/8bae9074-2c00-4a32-a421-ecdfae391101)

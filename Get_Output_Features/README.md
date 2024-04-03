# Visualization of layers' output
**Code:**
```
from tensorflow.keras import backend as K
train_data =[(example.numpy(), label.numpy()) for example, label in train_dataset]
layerIndex = 6
func = K.function([model.get_layer(index=0).input], model.get_layer(index=layerIndex).output)
fig, axs = plt.subplots(10,16,sharex=True)
fig.set_dpi(1000)
for i in range(10):
  for j in range(16):
   layerOutput = func([train_data[i][0]])  # input_data is a numpy array
   layerOutput=np.asarray(layerOutput,dtype=np.float32)
#print(layerOutput)
#for i in range(8):
   axs[i,j].imshow(layerOutput[0,:,20,:,j])
   axs[i,j].axis("off")

#plt.imshow(layerOutput[0,:,10,:,60])
```
![image](https://github.com/Ali-Mohammadnezhad/Keras_Colab/assets/110347490/f5aef679-08c3-4ba0-a116-c7b333faef2e)

# Visualization of layers' output
**Code:**
```
from tensorflow.keras import backend as K
train_data =[(example.numpy(), label.numpy()) for example, label in train_dataset]
layerIndex = 0
func = K.function([model.get_layer(index=0).input], model.get_layer(index=layerIndex).output)
fig, axs = plt.subplots(1,10,sharex=True)
fig.set_dpi(1000)
for i in range(10):
   layerOutput = func([train_data[i][0]])  # input_data is a numpy array
   layerOutput=np.asarray(layerOutput,dtype=np.float32)
#print(layerOutput)
#for i in range(8):
   axs[i].imshow(layerOutput[0,:,40,:,0])
   axs[i].axis("off")

#plt.imshow(layerOutput[0,:,10,:,60])
```

![image](https://github.com/Ali-Mohammadnezhad/Keras_Colab/assets/110347490/db9f1be1-1c7a-4f3d-abaa-1118f04af982)

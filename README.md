# opencv-for-darknet
Adjust opencv for darknet, Support CNN "relu" and maxpool "VALID"

## complie 
## get opencv  
```
#wget https://codeload.github.com/opencv/opencv/zip/4.0.1   
wget http://www.chineseocr.com:9990/static/models/opencv/opencv.4.0.1.zip    
 
unzip  opencv.4.0.1.zip && \
cp darknet_io.cpp opencv-4.0.1/modules/dnn/src/darknet && \
cp layers_common.cpp opencv-4.0.1/modules/dnn/src/layers && \
cp all_layers.hpp opencv-4.0.1/modules/dnn/include/opencv2/dnn/

```
### mac
```
cd opencv-4.0.1 && mkdir build && cd build && cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D BUILD_opencv_python2=OFF \
    -D BUILD_opencv_python3=ON  \
   -D PYTHON3_EXCUTABLE=~/anaconda3/envs/chineseocr/bin/python3 \
  -D PYTHON3_INCLUDE_DIR=~/anaconda3/envs/chineseocr/include/python3.6m  \
-D PYTHON3_LIBRARY=~/anaconda3/envs/opencv/lib/libpython3.6m.dylib \
-D PYTHON_NUMPY_PATH=~/anaconda3/envs/opencv/lib/python3.6/site-packages/numpy/core/include .. \
&& make -j2 && make install

 
```
### ubuntu
```
cmake -D CMAKE_BUILD_TYPE=RELEASE \
     -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D BUILD_opencv_python2=OFF \
    -D BUILD_opencv_python3=ON  \
   -D PYTHON3_EXCUTABLE=/usr/bin/python \
  -D PYTHON3_INCLUDE_DIR=/usr/include/python3.6m  \
-D PYTHON3_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython3.6m.so \
-D PYTHON_NUMPY_PATH=/usr/local/lib/python3.6/dist-packages/numpy/ .. \
&& make -j2 && make install
```

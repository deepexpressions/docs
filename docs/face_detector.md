 <h1>FaceDetector</h1>

`FaceDetector` is build on top of [OpenCV dnn](https://github.com/opencv/opencv/tree/master/samples/dnn) module which is based on the Single Shot Detector (SSD) framework with a ResNet base network. 

```python
DeepExpressions.FaceDetector()
```

 <h3>Usage:</h3>


```python
from matplotlib import pyplot as plt
from DeepExpressions import FaceDetector

# Load image
image = plt.imread("my-image.jpg")
# Create FaceDetector object
face_detector = FaceDetector()
# Compute faces locations in the image
bb_list = face_detector(image, size=(300,300), threshold=0.5)

# --> bb_list = [[x0, y0, x1, y1], [...]]
```

<h3>Arguments:</h3>



<h3>Returns:</h3>

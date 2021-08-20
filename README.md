# People Counter with OpenCv Deep Neural Network (DNN) 

## Debrief
- Accepts:
  - Input Video file either offline or live webcam
  - Output Video file to save
  -   
- Loads the OpenCV Deep Neural Network model stored in Caffe framework's format (readNetFromCaffe)
- Accepts 2 parameters
   - path to .prototxt with description of the network architecture
   - path to caffemodel file with learned network (MobileNetSSD)
      - MobileNetSSD is an object detection Single Shot Detector (SSD) model that computes   
         - bounding boxes
         - category of an objects
- Utilizes 2 custom python functions
   - TrackableObjects
   - CentroidTracking
- Image Processing use cv2.dnn.blobFromImage which performs:
    - performs Mean Subtraction
    - Scaling
    - Channel swapping
- ...accepts 
    - Input image (frame of the video)
    - Scale factor W, H (defaulted to 500px)
    - Size
    - Mean
  
Application:
1. in and out of a store
1. view of a security camera

Object Detection vs tracking:


Project Structure
```angular2html
.
├── Pipfile                         # required packages for code
├── README.md                       # you are here
├── main.ipynb                      # main jupyter notebook code
├── main.py                         # main python code
├── mobilenet_ssd                   # Caffe deep learning model
├── output                          # output generated from the model
├── requirements.txt                # required packages for code
├── submodules                      # helper scripts
│   ├── __init__.py
│   ├── centroidtracker.py    # track an objects center
│   └── trackableobject.py    # detect an object
└── videos                          # input videos if not using web cam
```

# References
1. https://www.pyimagesearch.com/2018/08/13/opencv-people-counter/
1. https://www.pyimagesearch.com/2018/07/23/simple-object-tracking-with-opencv/
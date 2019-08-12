# OpenCV Face Recognition
Use OpenCV to perform face recognition. To build our face recognition system.

## Technique
-------------
+ OpenCV
+ BlobFromImage
+ Numpy
+ Scikit-learn

### Issues
-----------
+ Doesn't detect someone who is wearing glasses.

+ Could detect two faces in an image.

+ Wrong detect when data changed

+ Need to improve the algorithm, make sure to detect in many cases.

### Prepare
------------
+ Get `openface.nn4.small2.v1.t7` from https://github.com/spmallick/PyImageConf2018/blob/master/FaceRecognition-Webapp/data/openface.nn4.small2.v1.t7

+ Get `face_dection_model` from https://github.com/kb22/Create-Face-Data-from-Images

### Usage
----------
+ Run docker compose
    ```
    docker-compose up
    ```

+ Excute
    ```
    docker exec -it opencv-deeplearning bash
    ```

+ Extract embeddings data
    ```
    python extract_embeddings.py --dataset dataset \
        --embeddings output/embeddings.pickle --detector face_detection_model
    ```

+ Train Model
    ```
    python train_model.py --embeddings output/embeddings.pickle \
        --recognizer output/recognizer.pickle --le output/le.pickle
    ```

+ Run recognize
    ```
    python recognize.py --detector face_detection_model --recognizer output/recognizer.pickle \
        --le output/le.pickle --image images/test3.jpg
    ```

+ Run on Jumpyter: Using recognize_jumpyter.py

### Reference
--------------
+ [OpenCV Face Recognition](https://www.pyimagesearch.com/2018/09/24/opencv-face-recognition/)
+ [Face Recognition with OpenCV and Deep Learning](https://www.pyimagesearch.com/2018/06/18/face-recognition-with-opencv-python-and-deep-learning/)
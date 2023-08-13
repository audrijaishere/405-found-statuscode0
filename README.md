# 405-found-statuscode0

Software :Face detection & Recognition software made on top of ML models
Problems it solves:'
1. Security verification
2. Attendance tracking 
3. Easy access for elderly

Hardware Usage: Camera

This software uses 3 neural networks ->
1. faceapi.nets.ssdMobilenetv1.loadFromUri('/models'): This line of code loads a pre-trained deep learning model called SSD Mobilenetv1, which is used for object detection and can be used for face detection

2. faceapi.nets.faceRecognitionNet.loadFromUri('/models'): This line loads another pre-trained deep learning model, specifically designed for face recognition. It loads the model from the '/models' URI.

3.faceapi.nets.faceLandmark68Net.loadFromUri('/models'): This line loads a model for facial landmark detection. It is used to identify key facial landmarks such as eyes, nose, and mouth



The webcam opens up once all the neural networks have loaded.

This program uses array 'labels' to store the elements for comparison. Once the inout from the camera is taken it compares it with all the array elements(pictures).

A loop operates using faceapi.js library to perform face detection, landmark detection, and descriptor extraction on each image. 


 results.forEach((result, i) => {
        const box = resizedDetections[i].detection.box;
        const drawBox = new faceapi.draw.DrawBox(box, {
          label: result,
        });
        drawBox.draw(canvas);
        if (result.distance < 0.6) {
          recognized = true;
          alert('Logged in successfully');
        } else {
          recognized = false;
          alert('New user, register now!');
        } 

this code snippet processes the results of face recognition, draws bounding boxes around detected faces on a canvas, and displays alerts based on the recognition distance. It provides a basic mechanism for user authentication and registration using face recognition.



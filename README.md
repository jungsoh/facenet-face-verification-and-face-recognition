# FaceNet: Face verification and face recognition
We will build a face recognition system using [FaceNet](https://arxiv.org/abs/1503.03832). Face recognition problems commonly fall into one of two categories:

- Face verification: "Is this the claimed person?" For example, at some airports, you can pass through customs by letting a system scan your passport and then verifying that you (the person carrying the passport) are the correct person. A mobile phone that unlocks using your face is also using face verification. This is a 1:1 matching problem.
- Face recognition: "Who is this person?" For example, this face recognition video of Baidu employees entering the office without needing to otherwise identify themselves. This is a 1:K matching problem, where K is the number of persons in the face database.

I did this project in the [Convolutional Neural Networks](https://www.coursera.org/learn/convolutional-neural-networks) course as part of the [Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning).

## Vector encoding of faces
FaceNet learns a neural network that encodes a face image into a vector of 128 numbers. By comparing two such vectors, you can then determine if two pictures are of the same person. We compute the distance between two encodings and apply a threshold to determine if the two encodings (thus the two pictures) represent the same person:

![Computing distance between encodings](images/distance_kiank.png)

Here are some examples of distances between the encodings between three individuals:

![Distance examples](images/distance_matrix.png)

We use a pre-trained FaceNet model to build both the face verification and recognition systems.

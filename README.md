# Face--Recognition-Detection--1
1 Image Processing
The microcomputer which contains the image processing unit embedded within it performs face detection and authorizes the person. The processing of images involves two parts, face detection, and face recognition.

2 Face Detection
The acquired image is processed to detect the face using the algorithm which effectively uses cascade object detection. Cascade detector detects acquire an image and extracts the face region from the acquired image. The face recognition system has stored the images of the face of an authorized person in a different environment. The face images are enhanced by normalizing them to remove the unwanted detailing due to illumination constraints while acquiring the image and are stored in the database. Now the face recognition task must be performed with the detected face and image stored in the database.

3 Face Recognition
Face recognition can be performed by different algorithms in OpenCV such as feature-based face recognition algorithm or model-based algorithm. Mostly feature-based algorithm used in real-time security systems. Principal Component Analysis (PCA) and Linear Discriminant Analysis (LDA) algorithms are efficient in terms of extracting the features to perform recognition. Both algorithms compared are the same in decrement to feature base algorithm, but Linear Discriminant Analysis (LDA) outperforms Principal Component Analysis (PCA) algorithm when large training sets are involved in recognition. LDA Also discriminates most of the present information in images efficiently by computing intraclass and inter-class scattered matrix. Using the databased stored images it performs the LDA and recognizes the difference between normalized images stored in the database and detected images. LDA performs the authorization of the image and gives further signals to the system. Since we have successfully detected the person using open CV and anaconda software-based image processing algorithm.

 
4. System Design
Face authentication and face identification are challenging problems. The fact that in the recent past, there have been more and more commercial, military and institutional applications makes the face recognition systems a popular subject.
The face recognition system is a system which will detect the human face in a video. The video is first converted into frames then the face recognition is done on each frame. The identified face will be transformed into eigenfaces. This eigenface will be matched with the pre stored eigenfaces by finding the euclidian distance between them. The eigenface with least euclidian distance is the one with whom the identified face resembles or the match is not fount. But a minute drawback of this technique is that the system is slow to identify the faces in video as it track the face and matches the tracked face with pre stored images in each frame of video which will take time if the motion in a video is slow for instance in a video a news reporter is delivering news will have least motion and in frame only one face will be recognized frequently in each frame which unnecessarily consumes time as the system will recognize the same face multiple times.
So as to overcome this drawback of traditional system, we are introducing a method of PCA with eigenfaces only on the key frames i.e the frames that have drastic change than the preceding frame in video. As the algorithm is applied only on key frames the time required to track and match all the faces in a video file will be very less than the previously established approach. The strategy of the Eigenfaces method consists of extracting the characteristic features on the face and representing the face in question as a linear combination of the so called „eigenfaces‟ obtained from the feature extraction process. The principal components of the faces in the training set are calculated. Recognition is achieved using the projection of the face into the space formed by the eigenfaces. A comparison on the basis of the Euclidian distance of the eigenvectors of the eigenfaces and the eigenface of the image under question is made. If this distance is small enough, the person is identified. On the other hand, if the distance is too large, the image is regarded as one that belongs to an individual for which the system has to be trained.
 

















5 Eigenfaces Method
The basis of the eigenfaces method is the Principal Component Analysis (PCA). Eigenfaces and PCA have been used by Sirovich and Kirby to represent the face images efficiently. They have started with a group of original face images, and calculated the best vector system for image compression. Then Turk and Pentland applied the Eigenfaces to face recognition problem . The Principal Component Analysis is a method of projection to a subspace and is broadly used in pattern recognition. An objective of PCA is the replacement of correlated vectors of large dimensions with the uncorrelated vectors of smaller dimensions. Another objective is to calculate a basis for the data set. Main advantages of the PCA are its low sensitivity to noise, the reduction of the requirements of the memory and the capacity, and the increase in the efficiency due to the operation in a space of smaller dimensions.











6 Key-frames
A video frame is a solo picture or motionless shot that is shown as a fraction of a larger video. Key-frame is the frame that can represent the content of a section of a video. The key-frames are the frames that have drastic changes than the previous frame. In the proposed system, the key-frame extraction is done with the help of a color histogram
The algorithm of color histogram is given below:
	Set ‘d’ as threshold and initialize the algorithm.
	Select the first frame and set it as key frame.
	If no frame is captured go to 6.
	Start the comparison of current captured frame with the selected key frame.
	Calculate the difference between them
	If the d> difference then select the current frame as next key frame.
	If the d> difference then go ‘c’.
	Go to next frame
	End.

7 Mathematical Model
A mathematical model is a description of a system using mathematical concepts and language. A model may help to explain a system and to study effects of different components of a system to predict the behavior of system.
The mathematical modeling for our system is as follows
S= {∑, F, δ, C}
S = Face Recognition.
∑ = set of input symbols = {Video File, image, character
information}
F = set of output symbol = {Match Found then notification to
user, Not Found}
δ =   1. Start
	Read training set of N×N image
	Resize image dimensions to 〖N 〗^2×1
	Select training set of〖 N〗^2×M
Dimensions, M: number of sample images
	Find average face, subtract from the faces in the training set, create matrix A
ψ=1/M ∑_(i=1)^M▒〖Гi 〗

Where,
Ψ= average image,
M= number of images, and
Гi= image vector.
Φi = Гi – Ψ
Where, i = 1, 2, 3, …, M.
A = [Φ1, Φ2, Φ3…ΦM]
	Calculate covariance matrix: AA'
C= A^T×A

	Calculate eigenvectors of the c covariance matrix.
	Calculate eigenfaces = No. of training images –no. of classes (total number of people) of eigenvectors.
	Create reduced eigenface spaceThe selected set of eigenvectors are multiplied by the A matrix to create a reduced eigenface
	Calculate eigenface of image in question.
	  Calculate Euclidian distances between the image and the eigenfaces.
	Find the minimum Euclidian distance.
	Output: image with the minimum Euclidian distance or image unrecognizable
C = {The system will not process the audio data, Eigenfaces will generate the grayscale images, The algorithm will run only on key frames.}

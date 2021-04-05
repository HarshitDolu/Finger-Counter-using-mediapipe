# Finger-Counter-using-mediapipe

## Team Project:

1. Harshit Jain 18UCS104
2. Swarnendu Ganguli 18UCS068
3. Rhea Ravi Sharma 18UCS111

MediaPipe is a cross-platform framework for building multimodal applied machine learning pipelines.

## ML Pipeline

MediaPipe Hands utilizes an ML pipeline consisting of multiple models working together: A palm detection model that operates on the full image and returns an oriented hand bounding box. A hand landmark model that operates on the cropped image region defined by the palm detector and returns high-fidelity 3D hand keypoints. This strategy is similar to that employed in our MediaPipe Face Mesh solution, which uses a face detector together with a face landmark model.

Providing the accurately cropped hand image to the hand landmark model drastically reduces the need for data augmentation (e.g. rotations, translation and scale) and instead allows the network to dedicate most of its capacity towards coordinate prediction accuracy. In addition, in our pipeline the crops can also be generated based on the hand landmarks identified in the previous frame, and only when the landmark model could no longer identify hand presence is palm detection invoked to relocalize the hand.

The pipeline is implemented as a MediaPipe graph that uses a hand landmark tracking subgraph from the hand landmark module, and renders using a dedicated hand renderer subgraph. The hand landmark tracking subgraph internally uses a hand landmark subgraph from the same module and a palm detection subgraph from the palm detection module.

<p align="center">
<img src="https://github.com/HarshitDolu/Finger-Counter-using-mediapipe/blob/main/info.png" width="500" height="500"/>
</p>



### Project Flow:

Hand Tracking model from media pipe. Each hand is having landmarks comprise of 21 points.
Goal is to count fingers in the right hand.
First stored tip id of fingers in list.
Next compare the co-ordinates to check whether finger is open or close.
If open, append 1 in list and for close fingers append 0 in list.
At last count total fingers and dispay it using its corresponding image and cv2.putText the count of fingers.

Video access Link: <a href="https://drive.google.com/file/d/1DywwWep3h_pIXfMfBrThQmvijBNGhUQd/view?usp=sharing">Explaination and demo Link</a>


### Demo images

<p align="center">

  
<img src="https://github.com/HarshitDolu/Finger-Counter-using-mediapipe/blob/main/demo1.jpeg" width="600"/>
<img src="https://github.com/HarshitDolu/Finger-Counter-using-mediapipe/blob/main/demo2.jpeg" width="600"/>
</p>

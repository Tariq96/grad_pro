# Humanoid Avatar Robot
## Abstract
This project represents a method for controlling Humanoid Robots using motion transfer or “do as I do”, given a video feed of a person moving, we can immediately transfer his motion to a humanoid robot, frame by frame motion transfer. Using pose detection as an intermediate representation between the source and the target to map all the source motion to the target humanoid robot. And Transferring the Robot environment back to the source in order to react and interact with it.

## Theory
The main idia is to transfer the human source into distant environment by transferring his motion to the Humanoid robot and transferring the robot’s surrounding environment back to the Human source using virtual reality technology, making his every intuitive move applicable to the Humanoid robot as long as it have the degrees of freedom to support it , which makes the whole experience immersive.
Transferring motion between human subjects and Humanoid robots using camera live feed or a video of the person we wish to impose his motion and a Humanoid Robot whose motion we wish to synthesize.

To transfer motion between subject in image to humanoid robot frame by frame manner, we must set a mapping between the person in the image and the Humanoid Robot. 
Human body varies in shapes, lengths and clothes colors, properties that doesn’t affect the pose se we only decode the important details into stick figure representation that holds all the necessary information to re-act the human motion by the avatar robot, as in figure 1.

   ![figure 1](https://github.com/Tariq96/Humanoid_Avatra_Robot/blob/master/images/Capture.PNG)

 Then to obtain this motion the pose of the stick figure is taken by an algorithm “Lifting from the Deep” which propose a unified formulation for the problem of 3D human pose estimation from a single raw RGB image that reasons jointly about 2D joint estimation and 3D pose reconstruction to improve both tasks. It takes an integrated approach that fuses probabilistic knowledge of 3D human pose with a multi-stage CNN architecture and uses the knowledge of plausible 3D landmark locations to refine the search for better 2D locations. The entire process is trained end-to-end, is extremely efficient and obtains state-of-the-art results on Human3.6M outperforming previous approaches both on 2D and 3D errors. (http://visual.cs.ucl.ac.uk/pubs/liftingFromTheDeep)
So it takes the 2D representation from the pose detection algorithm and transform it into 3D representation by estimating the 3rd coordinate for every joint that yields in x,y,z coordinate for the stick figure .

Then using victor manipulation algorithm, we can extract the information needed to calculate the Humanoid Robot input in order to re-act the human source motion.
Moving the robot head is based on the VR headset gyroscope sensor in order to get more accurate and fluid movement tracking the head of the human source and sending its orientation to the humanoid robot in order to re-act the movement. A normal camera in the robot head transfer the surrounding frame by frame to algorithm that takes single image and make it suitable to be shown in the VR headset that the human source is wearing. 

![robot2](https://user-images.githubusercontent.com/28588004/87577346-0e632880-c6d3-11ea-9cfa-5c22b7c63efb.gif)


## Refrences 
1- https://github.com/ildoonet/tf-pose-estimation

2- https://github.com/DenisTome/Lifting-from-the-Deep-release

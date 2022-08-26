# MSDS462 – Computer Vision | Final Project | Self-Driving Car (a MVP)

## 1. Introduction
The automobile is arguably one of the most important inventions of the past two centuries. Aside from the implementation of safety features like airbags and seatbelts, though, for a while there hadn’t been many radical or widespread adjustments made to their overall designs. The industry has more than made up for that lapse in just the past couple of decades, introducing innovative designs such as electric engines, keyless ignition, connected vehicle systems and perhaps most exciting of all – an autonomous car!

The idea of a self-driving car is not new. It is even older than Modern computing Era. In  the General Motor’s Exhibit in 1939, Normal Bell Geddes created the first Self Driving car. This was an electric vehicle guided by Radio Controlled Electronic Field, but after Deep learning came in to picture in 2011–12’s, a lots of other problems with the Self-Driving-Car has seen a huge boost. According to Precedence Research, the self-driving cars market size is projected to surpass around USD 65 million units by 2030 and expanding growth at a CAGR of 13.38% over the forecast period 2022 to 2030, taking up to 25 billion USD in revenue

## 2. Standard Approach
There are five major components that make up a self-driving car:
* Computer Vision: how a car sees. The goal is to be able to identify objects near the car and its surroundings
* Sensor fusion: how a car understands its environment. The idea of sensor fusion is to being able to understand the environment in a detailed manner. Because there are a bunch of sensors equipped on a self-driving car, we can take all the necessary data and fuse them to provide a richer diagram to our car, hence the name sensor fusion.
* Localization: how a car knows its location. we can think it to be like a GPS system
* Path planning: how a car thinks about the most optimal route. It is like a navigator system
* Control: how a car control its functions. Consider this as any action that is required on a car, like handling the steering wheel, brake, accelerator and gear.

![image](https://user-images.githubusercontent.com/59175150/186892869-376317f9-4e65-4c60-afc6-8441fa89d86a.png)

A typical self-driving car system

## 3. Practical challenges and scope of work
* Data (video) collection over extended period 
* Scale of training data (100’s of TB of data)
* Computation resource and computation time (high end GPU clusters, RAM)
* Varying conditions - traffic, weather, location (different countries have different traffic rules)

This project is to develop a Minimum Viable Product (MVP) for a self-driving car is based on a research paper published in 2014 by Nvidia. They proposed the whole self-driving-car as a Regression Problem. They trained a model which takes picture of the car's front view and returns the angle of steering should be in that particular frame. A whole new 8 layer of Neural-network architecture was created which has Four Convolution Layers and Four dense layers.
![image](https://user-images.githubusercontent.com/59175150/186893019-5414794c-ba45-424d-88af-c3397386d64f.png)

## 4. Dataset
Sully Chen auto-pilot dataset: A video collected over Approximately 45,568 images, 2.25GB - 25 min video recording at 30 fps.  Video was recorded near Silicon Valley. He installed a front dash camera and he hacked his car’s OBD system to capture the steering angle at every millisecond.

## 5. Model
Convolutional Neural Network (CNN) is used to map the raw pixels from a front-facing camera to the steering commands for a self-driving car. This powerful end-to-end approach means that with minimum training data from humans, the system learns to steer, with or without lane markings, on both local roads and highways. The model architecture is as below.
![image](https://user-images.githubusercontent.com/59175150/186893406-21c4ae90-143c-4763-b07e-90f49e174f64.png)

Convolutional Neural Network (CNN) is used to map the raw pixels from a front-facing camera to the steering commands for a self-driving car. This powerful end-to-end approach means that with minimum training data from humans, the system learns to steer, with or without lane markings, on both local roads and highways.
![image](https://user-images.githubusercontent.com/59175150/186893443-5e8927e2-a0ff-4bb4-aeea-b77dab57ef74.png)

The Loss plot - (End-to-end Learning model, Nvidia):

![image](https://user-images.githubusercontent.com/59175150/186893494-3c4c8812-d0df-4e69-89e3-daa4e763e7f5.png)

## 6. Result
The End-to-end learning model as proposed by Nvidia works pretty well in this set up giving a MSE of 0.0209 on the validation (video) clip. We were able to successfully demonstrate using a small simulator showing changes to the steering angle with the car movement.

## 7. References
Website. “How to Build Self-Driving-Car Using End-to-End Deep_Learning..!!”
	https://medium.datadriveninvestor.com/how-to-build-self-driving-car-using-end-to-end-deep-learning-a36d14667570

Google Drive. “Sully Chen dataset”.
	https://drive.google.com/file/d/1PZWa6H0i1PCH9zuYcIh5Ouk_p-9Gh58B/view  

Website. “Self-Driving Car on Indian Roads”.
	https://www.soilcampus.com/aijstory/self-driving-car-on-indian-roads 

Bojarski, Mariusz, Testa, Davide Del, Dworakowski, Daniel, Firner, Bernhard, Flepp, Beat, Goyal, Prasoon, Jackel, Lawrence D., Monfort, Mathew, Muller, Urs, Zhang, Jiakai, Zhang, Xin, Zhao, Jake and Zieba, Karol. "End to End Learning for Self-Driving Cars." CoRR abs/1604.07316 (2016)
	https://arxiv.org/pdf/1604.07316.pdf


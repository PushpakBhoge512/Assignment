#  Task 1.1 - Data Visualization
Here you have to visualize the results on the images. In the folder "Data Visualization" there are two folder
1. Images - Contains images named as 1.jpg, 2.jpg and so on
2. Data - Contains metadata in form of JSON file named as 1.json, 2.json and so on

The naming is consistant between them for example 1.json is the metadata for image 1.jpg. In the json file you will find normalized xy  co-ordinates of polygons and class of the polygon., alongwith which side of car it is (passenger side, front side, driver side etc.) 

For normalizing the co-ordinates following formula is used
normalized_x = ( x / image_width ) * 100
normalized_y = ( y / image_height ) * 100

Hint --> masks and alpha blending
### Following is the breakdown of the task:
1. You have to go through json and figure out which fields to use and which field is for what.
2. You will need to denormalized the polygon co-ordinates to use them to plot on image
3. This polygons need to be plotted on image with transparancy and border highlighted with darker shade of same color (see an example of how it should look below)
4. You have to do total 2 types of visualiztion
	1.	Where only transparnt polygons are drawn
	2.	where bounding boxes are drawn around them and class of polygon   displayed some on corner (can choose any corner)

Examples
Visualiztion of first type (Same with not bounding box)
Notice that the border of area and bbox have similar color but darker shade
![Visualiztion of first type](https://drive.google.com/uc?export=view&amp;id=1fb8BNtQa2Sde2LwcjuVLb8_oarcR17Jg)
Visualiztion of Second type but without the confidende score
![Visualiztion of Second type](https://drive.google.com/uc?export=view&amp;id=14YRKrlBWK--mm_5ct7abpPG3yGjKp3og)

Note - How  much transparnt the polygon should be as per your taste but the parameter should be tweakble. also implementation using using low level function or from scratch will be prefered over high level one line implementation (e.g. detectron2 visualizer class)

#  Task 1.2 - Damage Identification
Here you have to identify the following things
1. How many damages on the car-part
2.  percentage of damage with respect to area of car part 

In the folder "Data Visualization" there are two folder

1. Images - Contains images named as 1.jpg, 2.jpg and so on
2. Data - Contains metadata in form of JSON file named as 1-car-parts.json, 1-damages.json, 2-car-parts.json, 2-damages.json and so on

The naming is consistant between them for examplet **1-car-parts.json** contains car-parts related metadata **1.damages.json** contains metadata for damages on car. The format for both json is excately same as the format in task1

### Following is the breakdown of the task:
1. You will find polygons of the car-parts (bumper, door, window) etc  and side of the car (front, back, driver-front corner etc ) in the car-parts.json files. Also you will find all the damages for that car in damages.json file
2. You need to match  the polygons of car part with that of damages and find out following things	
	1. Find out How many parts are damaged and parts that are not damaged
	2. How many damages and what type are on the damaged parts (for example there one scratch on Bumper and one crack, you will find damage type in polygon class in metadata) 
	3. After you have to calculate area of the damages on every damaged car part.
	4. Then you have to find the percentage of the carpart damaged (damaged_area / car_part_area) * 100
	5. bonus point if you could identify the part i.e. front driver side wheel, front Bumper etc. (you will find whihc side of car it is in metadata json)

You basically have to identify where are the damages and how percentage of damage on the car. Feel free to use your own judgement where you might have doubts.

### Instructions related to how to submit code
1. You have to create a util.py file in which you will put all of your helper functions.
2. For Task 1.1 main funtion should have mandatory parameteres image_path, meta_data_json_path and opacity as optional parameter (this will control transparancy). You can add as many arguments as you want but they should be optional
3. For Task 1.1 The function should return two images (list) of the same shpe as input image one for each type of visualiztion. image can be pillow or numpy array as per your choice
4. For Task1.2  it should return all the info as per discription How you want to return is upto you to decide. You can return a dictionary having all info  (you can decide the structure) or a list of strings like ["found x dents, y scratch on part xyz with percentage xx.xx", “found x dents, y scratch on part xyz with percentage xx.xx”]
5. You need to import this functions from the util.py file in a notebook where you will call them on images and display the results by plotting.
6. You have to put all the code in a folder with notbook named as demo.py put it in you github and share the repository link. (zip files will not be entertained)

### Things to Note
1. The submission should be through Github repo zip files will not be accepted
2. Make sure the code is running and there are no errors. put requirements.txt so no version related errors pop up

#  Task 2.1 - Damage Classifer
**Objectives :-** You have to train a binary classifier to check if the car is damged or not DataSets you can use 
 https://www.kaggle.com/anujms/car-damage-detection
You can label more data or use any other dataset you may find on internet it's upto you
You can use any framework you want pyTorch and TensorFlow
1. create a notebook on kaggle or colab (both fine)  it should have data preperation, training and evaluation code in it
2. Provide the Class weights drive link will work (bouns point if you could directly download the class weights without requiring to manually set)
3. Put the approach you have taken, augumentation policy you used, evaluation methods you have used and why etc in the notebook as markdown
#  Task 2.2 - Damage Detection
**Objectives :-** You have to train a bbox detection or instance segmentation or Semantic segmentation model to detect damages on cars. You can use following datasets. 
https://www.kaggle.com/ruby09/damage-detection-dataset
https://www.kaggle.com/eashankaushik/car-damage-detection
You can label more data or use any other dataset you may find on internet it's upto you
You can use any framework you want pyTorch(detectron2) and TensorFlow(object Detection API)
1. create a notebook on kaggle or colab (both fine)  it should have data preperation, training and evaluation code in it
2. Provide the Class weights drive link will work (bouns point if you could directly download the class weights without requiring to manually set)
3. Put the approach you have taken, evaluation methods you have used and why etc in the notebook as markdown
4. Put which of the method you have used ( bbox detection or instance segmentation or Semantic segmentation and why ) in markdown cell

### Instructions related to how to submit code
1. You have to use a notebook colab or kaggle any one is fine  you can either share the link directly or share it in github repo.
2. The notebook should contain all the things asked in task discription
3. You also need to put the experiment you have done and how you improved the model
4. You are not expected to have 80-100% accuracy but good enough which can do good enough on val sets in the datasets 


### Criteria
1. Structure and readbility of code
2. What methods are used (using high level function will not be prefered)
3. How well the code does on test cases

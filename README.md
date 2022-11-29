:warning: Please go throught the submission guidelines, if not followed the submission will not be considered (P.S. no zip files)

#  Task 1 - Damage Identification
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
3) your target is to do this in best optimized way

You basically have to identify where are the damages and how percentage of damage on the car. Feel free to use your own judgement where you might have doubts.

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
1. create a repository on your github account you can create new one or fork this one both is fine
2. add your code in the format and structure you would like
3. You have to do task1 mandatory and you can choose any one from task 2.1 and 2.2
4. For Task1 it should return all the info as per discription How you want to return is upto you to decide. You can return a dictionary having all info  (you can decide the structure) or a list of strings like ["found x dents, y scratch on part xyz with percentage xx.xx", “found x dents, y scratch on part xyz with percentage xx.xx”]
5. Do note that all the main code that you are writing should be *.py files 
6. You can colab or kaggle for task 2, but you will have to commit that notebook into the forked repo, also you will have yo track all the training data and different expeiment that you have done
7. a requirements.txt should be present in repo root directory
8. lastly there should be a notebook in root (home) directory of repo named "demo.ipynb" it should contain all the report, summary of task 1 and 2
9. for example for task 1 importing functions from *.py files and print out the results with any visulization and for example 2 it should have all the information you can add realted to task2 like code for running model on test set and report on different experiments their logs and why you chose the model
10. remember 'demo.ipynb' is only for demo all the major logic should be in *.py files and all the outputs should be cached in notebook they should not be cleared
11. share the public github url of your repository


### Criteria of evaluation
1. Structure, redability of the project and code
2. does the code run out of the box (like just by doing `pip install -r requirements.txt`)
3. how the dependencies are handled
4. choice of model, usage of different training stratagies and understanding of concept
4. How well the core python code is written
5. How well the code does on test cases

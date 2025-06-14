1. gather all the trafic light image in image folder and video for test at end
2. using a Label studio annotate a red and green light and export it to yolo format.
3.yolo formate give in zip formate unzip file name is project.zip unzip it.
4. this file have a image, label, class.txt and notes.json5. 
5.then create a train and val folder. within that add image and label from project split according to your use
6.then create a yaml file inthat add nescesary details.
7. now create a yolov11.ipynb for model implementaion.
8. run , after that run file is created. if u want to modify the nput image u need to remove the catch file.
8.so to run- train-weights- best.pt we are intrested. copy this paste in root folder and rename as YOLOv11_custom.pt
9. now the prediction step. write a code in jupyter
10. run the pridiction model, in run prediction file there will be a predicted image detection. same for video also.
   

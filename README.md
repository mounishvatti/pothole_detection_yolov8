# pothole_detection_yolov8
Pothole Detection on roads and custom datasets using YOLOv8

<H1 align="center">
YOLOv8 Segmentation with DeepSORT Object Tracking(ID + Trails) </H1>

## Google Colab File Link (A Single Click Solution)
The google colab file link for yolov8 segmentation and tracking is provided below, you can check the implementation in Google Colab, and its a single click implementation
,you just need to select the Run Time as GPU, and click on Run All.

[`Google Colab File`](https://colab.research.google.com/drive/17SLXw-wdHG2syQhLSHH5r5_rkZx5poo0)


## Object Segmentation and Tracking (ID + Trails)  using YOLOv8 on Custom Data


## Steps to run Code

- Clone the repository
```
git clone https://github.com/mounishvatti/pothole_detection_yolov8.git
```
- Goto the cloned folder.
```
cd pothole_detection_yolov8
```
- Install the Dependencies
```
!pip install ultralytics
```
```
!pip install fastapi kaleido python_multipart uvicorn
```
- Setting the Directory.
```
%cd {HOME}

```
- Downloading the Datasets From The Google Drive 
```
https://drive.google.com/drive/folders/1Bt1ghpewGpPnX696u-TEHaUCrH85AKtw
```
- Downloading a Demo Video from the Google Drive
- Demo Video 
```
gdown "https://drive.google.com/file/d/1xDzURxmF6OWQWc2RIkn_0PbSFZOqhnY8/view?usp=drive_link"
```

- Run the code with mentioned command below.
- For training the data
```
!yolo task=detect mode=train model=yolov8m.pt data={dataset.location}/data.yaml epochs={number of epochs} imgsz=640

```
- For yolov8 segmentation + Tracking
```
!yolo task=detect mode=predict model={HOME}/runs/detect/train/weights/best.pt conf=0.25 source='/content/drive/MyDrive/demo.mp4'

```

### RESULTS

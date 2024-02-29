![3](https://github.com/mounishvatti/pothole_detection_yolov8/assets/76279858/5e5a2ea1-c512-4c86-b0e6-b8128c997503)

<H1 align="center">Image Segmentation & Pothole Detection</H1>

Firstly I'd like to thank Respected [Jagan Mohan Reddy](https://www.google.com/url?sa=i&url=https%3A%2F%2Fmail.teluguwishesh.com%2F190-andhra-headlines-flash-news%2F92168-ap-cm-ys-jagan-takes-a-nap-in-assembly-during-hot-debate-on-capital.html&psig=AOvVaw2KdWUaqEwDuEjsCPJFhmWA&ust=1708277670999000&source=images&cd=vfe&opi=89978449&ved=0CBMQjRxqFwoTCNjalrD0soQDFQAAAAAdAAAAABAE) - (CM AP) for not covering up the potholes in Andhra Pradesh as most of the data was collected from that state.

## Google Colab File Link (A Single Click Solution)
The google colab file link for yolov8 segmentation and tracking is provided below, you can check the implementation in Google Colab, and its a single click implementation
,you just need to select the Run Time as GPU, and click on Run All.

[`Google Colab File`](https://colab.research.google.com/drive/17SLXw-wdHG2syQhLSHH5r5_rkZx5poo0)

## Tech stack

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

## Object Segmentation and Tracking (ID + Trails)  using YOLOv8 on Custom Data

<h2>Clone the repository</h2>

```bash
!git clone https://github.com/mounishvatti/pothole_detection_yolov8.git
```
<h2>Goto the cloned folder</h2>

```bash
cd pothole_detection_yolov8
```
<h2>Install the Dependencies</h2>

```bash
!pip install ultralytics
```
```bash
!pip install roboflow
```
```bash
!pip install fastapi kaleido python_multipart uvicorn
```
<h2>Importing YOLO and a roboflow workspace for Image Segmentation</h2>

```python
from roboflow import Roboflow
rf = Roboflow(api_key="{the api key}")
project = rf.workspace("{name of workspace}").project("name-of-project")
dataset = project.version(1).download("yolov8")
```

> [!NOTE]
> If you are unable to perform the commands after importing the dataset from roboflow, you can access the same dataset from the drive link provided below, download it, upload it to your personal drive and mount the drive to your Google Colab 

<h2>Downloading the Datasets From The Google Drive</h2> 

[`Pothole Detection Dataset`](https://drive.google.com/drive/folders/18urMqJeUwPiVzsZ1HjwVBstzEyDLqmC4?usp=sharing)

<h2>Downloading the Potholes on a Road Video from the Google Drive</h2>

[`Potholes on Road Video`](https://drive.google.com/file/d/1MxNWhRhbAxFjY6S0iz8UsqYNZhiVePH_/view?usp=sharing)

<h2>My roboflow workspace containing the pothole dataset</h2>

[`Roboflow Workspace`](https://app.roboflow.com/vit-76kid/pothole-detection-project-3yiqt/1)

Run the code with mentioned command below.
- For training the data
```python
!yolo task=detect mode=train model=yolov8m.pt data={dataset.location}/data.yaml epochs={number of epochs} imgsz=640
```
- For yolov8 segmentation + Tracking & prediction
```python
!yolo task=detect mode=predict model={HOME}/runs/detect/train/weights/best.pt conf=0.25 source='/content/drive/MyDrive/demo.mp4'
```


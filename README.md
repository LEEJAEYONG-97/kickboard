
# Shared Scooter Parking Improvement Project
The project goal is to analyze shared scooter towing data and parking zones to identify patterns of illegal and unauthorized parking, while capturing relevant footage to visually demonstrate the issues, ultimately seeking solutions for parking improvement.

![image alt](https://github.com/LEEJAEYONG-97/kickboard/blob/2fd67c70a1ef3ba3a76fb876959644cd7cba1873/data/img/wordcloud.jpg)

# Data Collection

**Comprehensive information on Seoul's bike-sharing system (따릉이 대여소)**:

  Rental Stations, Location, latitude, longitude

**Data on Seoul's electric scooter towing incidents**:

  Towing Incidents, Report date, address, type

**Current status of electric scooter parking zones in Seoul**:

  Parking Zones, Location, latitude, longitude

**Nationwide administrative district code information**:

  Administrative Codes, Address

**Source**: DATA.GO.KR, data.seoul.go.kr

**Data common collection period**: July 2021 to September 2023

# Data Preprocessing Steps

1. **Date sorting**
2. **Type conversion**
3. **Missing value removal**

# EDA
**Exploratory Data Analysis (EDA)**

Seoul Electric Scooter Towing Incidents Chart

![image16](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/board.png)

Comparison Chart of Parking Areas for Seoul's Public Bikes (따릉이) and Electric Scooters

![image3](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/parking.png)

Seoul Electric Scooter Parking Areas

![image4](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/kickboardpark.png)

Map Showing Towing Incidents of Electric Scooters in Seoul

![image5](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/map.png)

Areas with High Towing Incidents: Gangnam

![image8](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/gangnam.png)

Areas with High Towing Incidents: Mapo

![image9](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/mapo.png)

# Model Design for Creating an Image Dataset with Roboflow

1. **Data Preparation**
   - Confirm image characteristics (resolution, format, etc.)
   - Organize images into appropriate folders (e.g., training, validation)
   - Annotate images as necessary

2. **Upload Images**
   - Upload the images to Roboflow
   - Ensure proper upload settings (e.g., image quality, format)

3. **Data Annotation**
   - Use Roboflow’s annotation tools to label images
   - Define classes and assign labels to each image

4. **Data Augmentation**
   - Apply augmentation techniques (e.g., rotation, flipping, scaling) to increase dataset variability
   - Review augmented images for quality and relevance

5. **Dataset Configuration**
   - Configure the dataset settings (e.g., image format, annotation format)
   - Set the desired output size for the images

6. **Data Splitting**
   - Split the dataset into training, validation, and test sets according to specified ratios

7. **Export Dataset**
   - Export the dataset in the desired format
![image12](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/roboflow.png)
![image13](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/roboflow2.png)

### YOLO (You Only Look Once)

YOLO is a state-of-the-art object detection algorithm known for its speed and accuracy. Unlike traditional object detection methods that typically apply a classifier to different sections of an image, YOLO approaches the problem as a single regression task, predicting bounding boxes and class probabilities directly from full images in one evaluation.

#### Key Features:
- **Real-time Detection**: YOLO processes images quickly, allowing for real-time object detection applications, making it suitable for use in video streams and live feeds.
- **Single Neural Network**: It uses a single convolutional neural network (CNN) that divides the image into a grid and predicts bounding boxes and class probabilities simultaneously.
- **Unified Architecture**: YOLO's unified architecture simplifies the detection process and enhances performance, as it eliminates the need for separate stages in the detection pipeline.

#### Advantages:
- **Speed**: YOLO can detect objects in images at an impressive frame rate, making it ideal for applications requiring quick responses, such as autonomous driving and surveillance.
- **Global Context**: By looking at the entire image rather than patches, YOLO captures contextual information, improving accuracy in detecting objects within their surroundings.

#### Applications:
YOLO is widely used in various fields, including:
- **Autonomous Vehicles**: For detecting pedestrians, vehicles, and obstacles.
- **Surveillance Systems**: To monitor areas for specific objects or behaviors.
- **Retail Analytics**: For counting customers or analyzing shopping behavior.


# Model Evaluation of YOLOv9
Performance Comparison of YOLOv9
![image15](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/result.png)
The YOLOv9 model demonstrates superior performance compared to other models, with the highest precision, recall, and mean Average Precision (mAP) scores.

# Model demonstration photo

![image7](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/captured_object.png)
![image14](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/processed_image%20(1).jpg)
![image10](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/20240804_201946633%20-%20frame%20at%200m17s.jpg)
![image24](https://github.com/LEEJAEYONG-97/kickboard/blob/f34fde72790d7dc973ee932cd16ffdd7ad8dc3b6/data/img/processed_image%20(3).jpg)

Indian Road Dataset (Mini Dataset)

1. Overview

This dataset is a mini subset created to support research on pedestrian intention prediction in real-world Indian road environments. The data consists of video-derived image frames annotated with pedestrian bounding boxes and crossing intention behavioral attributes.

2. Dataset Structure
Dataset/
│
├── images/
│   ├── video_01_0001.jpg
│   ├── video_01_0002.jpg
│   ├── video_01_0003.jpg
│   └── ...
│
├── annotations/
│   └── annotations.xml


images/: RGB image frames extracted from traffic videos

annotations/: XML file containing frame-wise pedestrian annotations

3. Annotation Format

Annotations are provided in XML format using a frame-based structure. Each image frame is represented by an <image> tag, and each pedestrian instance within a frame is annotated using a <box> tag.

3.1 Image-Level Tags

Each <image> tag contains:
id: Unique frame identifier
name: Image filename
width: Image width (pixels)
height: Image height (pixels)

3.2 Pedestrian Bounding Boxes

Each pedestrian is annotated using a <box> tag with the following attributes:
label: Object class (Pedestrian)
source: Annotation method (semi-auto)
occluded: Visibility flag (0 = visible , 1= occluded)
xtl, ytl: Top-left bounding box coordinates (pixels)
xbr, ybr: Bottom-right bounding box coordinates (pixels)

3.3 Pedestrian Attributes
Each pedestrian bounding box includes semantic and intention-related attributes:

Attribute	Description
action	Pedestrian action (e.g., Walking)
id:	Unique pedestrian track ID across frames
cross	Crossing intention (Crossing / Non-crossing)
look	Gaze behavior toward traffic (look / no-look)

These attributes enable behavior-aware and temporal intention analysis.

4. Intended Tasks

The dataset can be used for:
Pedestrian detection
Pedestrian crossing intention prediction
Behavior-aware pedestrian analysis
Frame-level pedestrian tracking using ID consistency

5. Data Collection and Preprocessing
Videos were captured in urban Indian traffic environments
Videos were converted into frame-level RGB images
Annotations were generated using a semi-automatic process with manual verification

6. Ethical Considerations
Data was collected from public road environments
No personally identifiable information is intentionally included
The dataset is intended for research purposes only
Commercial use is not permitted

7. Usage Notes
Bounding box coordinates are in pixel format
Intention labels are provided at the pedestrian (object) level
Temporal reasoning can be performed using pedestrian IDs across frames

8. Limitations
This is a mini dataset subset provided for reproducibility
Only pedestrian class annotations are included
Environmental factors such as weather or lighting are not explicitly labeled
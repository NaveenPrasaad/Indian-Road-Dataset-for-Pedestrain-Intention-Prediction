Indian Road Pedestrian Intention Dataset (Lite Version)
Overview

The Indian Road Pedestrian Intention Dataset ((Lite Version) is a curated subset designed to support research on pedestrian intention prediction in real-world Indian traffic environments.

The dataset contains image frames extracted from traffic videos along with pedestrian bounding box annotations and behavioral attributes related to crossing intention.

This dataset enables research in:

Pedestrian detection
Pedestrian crossing intention prediction
Behavior-aware pedestrian analysis

Dataset Structure
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

images/
RGB image frames extracted from traffic videos.

annotations/
XML file containing frame-level pedestrian annotations.

Annotation Format

Annotations are provided in XML format using a frame-based structure.
Each image frame is represented by an <image> tag, and each pedestrian instance within the frame is annotated using a <box> tag.

Image-Level Tags

Each <image> tag contains the following attributes:

Attribute	Description
id	Unique frame identifier
name	Image filename
width	Image width (pixels)
height	Image height (pixels)
Pedestrian Bounding Box

Each pedestrian instance is annotated using a <box> tag with the following attributes:

Attribute	Description
label	Object class (Pedestrian)
source	Annotation method (semi-auto)
occluded	Visibility flag (0 = visible, 1 = occluded)
xtl	Top-left X coordinate
ytl	Top-left Y coordinate
xbr	Bottom-right X coordinate
ybr	Bottom-right Y coordinate
Pedestrian Behavioral Attributes

Each pedestrian bounding box includes behavioral and intention-related attributes:

Attribute	Description
action	Pedestrian action (e.g., walking)
id	Unique pedestrian track ID across frames
cross	Crossing intention (crossing / non-crossing)
look	Gaze behavior toward traffic (look / no-look)

These attributes enable behavior-aware pedestrian intention analysis and temporal modeling.

Example Annotation
<image id="1" name="video_01_0001.jpg" width="1920" height="1080">
  <box label="Pedestrian" source="semi-auto" occluded="0" xtl="350" ytl="420" xbr="410" ybr="620">
      <attribute name="action">walking</attribute>
      <attribute name="id">5</attribute>
      <attribute name="cross">crossing</attribute>
      <attribute name="look">look</attribute>
  </box>
</image>

Intended Tasks

The dataset can be used for the following research tasks:
Pedestrian detection
Pedestrian crossing intention prediction
Behavior-aware pedestrian analysis
Multi-frame pedestrian tracking using consistent IDs


Data Collection and Preprocessing

Videos were captured in urban Indian traffic environments.
Videos were converted into frame-level RGB images.
Pedestrian annotations were generated using a semi-automatic annotation pipeline followed by manual verification.

Usage Notes

Bounding box coordinates are provided in pixel format.
Intention labels are provided at the pedestrian (object) level.



Ethical Considerations

Data was collected from public road environments.
No personally identifiable information is intentionally included.
The dataset is intended strictly for academic research purposes.

Limitations

This dataset is a mini subset released for reproducibility.
Only pedestrian class annotations are included.
Environmental conditions such as weather or lighting variations are not explicitly labeled.

License

This dataset is released for academic research purposes only.
Commercial use, redistribution, or modification for commercial purposes is not permitted without permission from the authors.

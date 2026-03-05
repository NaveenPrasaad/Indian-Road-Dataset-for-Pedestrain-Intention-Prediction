# Indian Road Dataset for Pedestrian Intention Prediction (Lite Version)

# 1.Overview
The Indian Road Dataset for Pedestrian Intention Prediction (Lite Version) is a curated subset designed to support research on pedestrian intention prediction in real-world Indian traffic environments.
The dataset contains image frames extracted from traffic videos along with pedestrian bounding box annotations and behavioral attributes related to crossing intention.<br>

This dataset enables research in:
Pedestrian detection<br>
Pedestrian crossing intention prediction<br>
Behavior-aware pedestrian analysis

# 2.Dataset Structure
```
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
```
images/
RGB image frames extracted from traffic videos.

annotations/
XML file containing frame-level pedestrian annotations.

# 3.Annotation Format

Annotations are provided in XML format using a frame-based structure.
Each image frame is represented by an <image> tag, and each pedestrian instance within the frame is annotated using a <box> tag.

**Image-Level Tags:** <br>

Each <image> tag contains the following attributes:<br>
</Markdown>
- id - Unique frame identifier<br>
- name - Image filename<br>
- width -Image width (pixels)<br>
- height - Image height (pixels)<br>

**Pedestrian Bounding Box:** <br>
Each pedestrian instance is annotated using a <box> tag with the following attributes:<br>
</Markdown>
- label -	Object class (Pedestrian)<br>
- source -	Annotation method (semi-auto)<br>
- occluded - Visibility flag (0 = visible, 1 = occluded)<br>
- xtl -	Top-left X coordinate<br>
- ytl	- Top-left Y coordinate<br>
- xbr -	Bottom-right X coordinate<br>
- ybr	- Bottom-right Y coordinate<br>

**Pedestrian Behavioral Attributes:** <br>
Each pedestrian bounding box includes behavioral and intention-related attributes:<br>
</Markdown>
- action- Pedestrian action (e.g., walking)<br>
- id- Unique pedestrian track ID across frames<br>
- cross- Crossing intention (crossing / non-crossing)<br>
- look- Gaze behavior toward traffic (look / no-look)<br>

These attributes enable behavior-aware pedestrian intention analysis and temporal modeling.<br>

Example Annotation
```
<image id="1" name="video_01_0001.jpg" width="1920" height="1080">
  <box label="Pedestrian" source="semi-auto" occluded="0" xtl="350" ytl="420" xbr="410" ybr="620">
      <attribute name="action">walking</attribute>
      <attribute name="id">5</attribute>
      <attribute name="cross">crossing</attribute>
      <attribute name="look">look</attribute>
  </box>
</image>
```

# 4.Intended Tasks

The dataset can be used for the following research tasks:
Pedestrian detection<br>
Pedestrian crossing intention prediction<br>
Behavior-aware pedestrian analysis<br>
Multi-frame pedestrian tracking using consistent IDs<br>

# 5.Data Collection and Preprocessing

Videos were captured in urban Indian traffic environments.<br>
Videos were converted into frame-level RGB images.<br>
Pedestrian annotations were generated using a semi-automatic annotation pipeline followed by manual verification.<br>

Usage Notes<br>
Bounding box coordinates are provided in pixel format.<br>
Intention labels are provided at the pedestrian (object) level.<br>

# 6.Ethical Considerations

Data was collected from public road environments.<br>
No personally identifiable information is intentionally included.<br>
The dataset is intended strictly for academic research purposes.<br>

# 7.Limitations

This dataset is a mini subset released for reproducibility.<br>
Only pedestrian class annotations are included.<br>
Environmental conditions such as weather or lighting variations are not explicitly labeled.<br>

# 8.License

This dataset is released for academic research purposes only.<br>
Commercial use, redistribution, or modification for commercial purposes is not permitted without permission from the authors.<br>


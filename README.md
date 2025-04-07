# 🚘 CarDD Dataset

CarDD is a novel, public, large-scale dataset specifically designed for vision-based car damage detection and segmentation.

The dataset contains **4,000 high-resolution car damage images** with over **9,000 well-annotated instances**, making it the largest public dataset of its kind. 

The high resolution of the images (average 684,231 pixels) is a key advantage over existing datasets that have a much lower average resolution (50,334 pixels). Higher resolution allows for more detailed annotations and the potential to detect finer damages.

### CarDD Dataset Overview and Features

CarDD features **six common external car damage categories**, chosen based on frequency of occurrence and clear definitions from insurance claim statistics.

1. Dent

2. Scratch

3. Crack

4. Glass shatter

5. Tire flat

6. Lamp broken 

*   The dataset provides **comprehensive annotations for multiple computer vision tasks**, including:
    *   **Classification:** Identifying the type of damage.
    *   **Object Detection:** Locating the damaged regions with bounding boxes.
    *   **Instance Segmentation:** Precisely outlining the damaged areas with pixel-level masks.
    *   **Salient Object Detection (SOD):** Identifying the damaged regions as salient objects through binary maps.


For object detection and instance segmentation, the annotations include **masks and bounding boxes** associated with each of the six damage types. Each instance has a unique ID, category information, mask contours, and bounding box coordinates, following the COCO dataset format. For SOD, pixel-level binary ground truth maps are provided.


### Annotation process
The **annotation process** involved experts from the car insurance industry and trained annotators following specific guidelines based on insurance claim standards. 

These guidelines address challenges like 

• mixed damages (priority rules)

• damages across components (boundary splitting)

• adjacent same-class damages (boundary merging). 

### Dataset splits
The dataset is split into **training (70.4%), validation (20.25%), and test (9.35%) sets**, maintaining a consistent ratio of instances for each category across the splits. 

Near-duplicate images were explicitly removed to prevent data leakage.

### Uses
*   CarDD presents several **challenges** for model development due to the nature of car damage:
    *   **Fine-grained distinctions** between damage types like dents and scratches.
    *   **Diversity in object scales and shapes** of the damages.
    *   A **significant proportion of small objects**, particularly for dent, scratch, and crack categories.
    *   The fact that damages like **dent, scratch, and crack can be intertwined and visually similar**.


#### Availability
The CarDD dataset is **publicly available** at https://cardd-ustc.github.io. However, access requires agreeing to the license terms of Flickr and Shutterstock, as the dataset does not own the copyright of the images. The dataset is intended for non-commercial research and educational purposes. Measures were taken to protect user privacy by mosaicking or deleting faces and license plates.



# Citation

```bibtex
@ARTICLE{CarDD, author={Wang, Xinkuang and Li, Wenjing and Wu, Zhongcheng}, 
journal={IEEE Transactions on Intelligent Transportation Systems}, 
title={CarDD: A New Dataset for Vision-Based Car Damage Detection}, 
year={2023}, 
volume={24}, 
number={7}, 
pages={7202-7214}, 
doi={10.1109/TITS.2023.3258480}}
```
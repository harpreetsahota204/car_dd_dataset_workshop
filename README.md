# 🚘 CarDD Dataset

CarDD (Car Damage Detection) is the **first public large-scale dataset** specifically designed for vision-based car damage detection and segmentation. 

It contains **4,000 high-resolution car damage images** with over **9,000 well-annotated instances** across six distinct damage categories. The dataset is intended to facilitate research in vehicle damage assessment by providing a high-quality, publicly available resource where previous efforts were hindered by insufficient or private datasets. 

CarDD supports multiple tasks, including classification, object detection, instance segmentation, and salient object detection (SOD).

<img src="cardd-overview-lq.gif">


**Curated by**: **Xinkuang Wang, Wenjing Li, and Zhongcheng Wu**. They are affiliated with the High Magnetic Field Laboratory, HFIPS, Chinese Academy of Sciences, Hefei, China, and the University of Science and Technology of China, Hefei, China, as well as the High Magnetic Field Laboratory of Anhui Province, Hefei, China.

 **Funded by**: This work was supported in part by the **Key Program of Research and Development of Hefei Science Center, CAS**, under Grant 2019HSC-KPRD003; in part by the **Hefei Comprehensive National Science Center** through the Pre-research Project on Key Technologies of Integrated Experimental Facilities of Steady High Magnetic Field and Optical Spectroscopy; and in part by the **Hefei Comprehensive National Science Center and the High Magnetic Field Laboratory of Anhui Province**.

## **Dataset Structure**

*   The CarDD dataset contains **4,000 high-resolution car damage images** with over **9,000 labeled instances**.

*   It covers **six damage categories**: **dent, scratch, crack, glass shatter, lamp broken, and tire flat**.

*   The dataset supports **four tasks**: classification, object detection, instance segmentation, and salient object detection (SOD).

*   **Image Quality**: Images are high-resolution, with an average resolution of **684,231 pixels** (13.6 times higher than the GitHub dataset) and an average file size of 739 KB. The lowest resolution is 1,000×413 pixels. Images are free of watermarks.

### **Annotations**

*   For **object detection and instance segmentation**, annotations are in a format consistent with the **COCO dataset**, providing a unique ID, damage category, point coordinates on mask contours, and bounding box locations for each instance. Tight-fitting bounding boxes are derived from pixel-level polygonal segmentation masks.

*   For the **SOD task**, the format is consistent with the **DUTS dataset**, offering pixel-level ground truth binary maps where objects are activated with a grayscale value of 255 and background is 0.

*   An **Excel file is attached** to the dataset, detailing the number of instances, number of damage categories, damage severity, and shooting angle for each image.

*   **Object Scales**: Instances are classified into three scales: "small" (area < 128^2 pixels), "medium" (128^2 ≤ area < 256^2 pixels), and "large" (area ≥ 256^2 pixels). The proportions are **38.6% small, 32.6% medium, and 28.8% large** instances.

*   **Diversity**: The dataset features diverse samples regarding shooting angles and vehicle colors.

## **Dataset Creation**

The dataset was created to address the significant lack of **high-quality, publicly available datasets** for vision-based car damage detection. 

Existing research was often conducted on private datasets, which hindered fair comparison of different approaches and limited the advancement of the field. CarDD aims to facilitate research by providing a large-scale, well-annotated dataset that exposes the challenges of car damage detection and segmentation. 

Previous public datasets were either small, focused only on classification, lacked sufficient labels, or had low resolution.

### **Source Data**:

**Data Collection and Processing**:
    1.  **Raw Data Collection**: A large number of images were **crawled from Flickr and Shutterstock**. These platforms were chosen for their provision of high-quality images and rich diversity in terms of damage types, viewpoints, light conditions, camera distance, and shooting angles.
    
    2.  **Duplicate Removal**: Duplicated images were automatically removed using "Duplicate Cleaner" and then manually double-checked.

    3.  **Candidate Selection**: An initial batch of 500 manually selected car damage images was used to **train a binary classifier based on VGG16**. This classifier was then used to automatically classify newly collected raw images as "damaged" (positive) or "undamaged" (negative), generating over 10,000 candidate images.

    4.  **Manual Filtering**: From the candidates, **4,000 damage samples** covering the six target classes were manually picked. Images with categories outside the scope (e.g., rusty, burned, smashed cars) were separated without annotations for potential future research.

    5.  **Privacy Protection**: Pictures containing user information, such as **human faces or license plates, were mosaicked or directly deleted** to ensure user privacy.

he source data producers are primarily the **users and contributors of Flickr and Shutterstock** who uploaded the original images.

### Annotation process

The **annotation process** involved experts from the car insurance industry and trained annotators following specific guidelines based on insurance claim standards. 

These guidelines address challenges like 

• mixed damages (priority rules)

• damages across components (boundary splitting)

• adjacent same-class damages (boundary merging). 

For object detection and instance segmentation, the annotations include **masks and bounding boxes** associated with each of the six damage types. 

Each instance has a unique ID, category information, mask contours, and bounding box coordinates, following the COCO dataset format. 

For SOD, pixel-level binary ground truth maps are provided.

### Dataset splits
The dataset is split into **training (70.4%), validation (20.25%), and test (9.35%) sets**, maintaining a consistent ratio of instances for each category across the splits. 

Near-duplicate images were explicitly removed to prevent data leakage.

### Uses

The dataset provides **comprehensive annotations for multiple computer vision tasks**, including:
    *   **Classification:** Identifying the type of damage.
    *   **Object Detection:** Locating the damaged regions with bounding boxes.
    *   **Instance Segmentation:** Precisely outlining the damaged areas with pixel-level masks.
    *   **Salient Object Detection (SOD):** Identifying the damaged regions as salient objects through binary maps.


CarDD presents several **challenges** for model development due to the nature of car damage:
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
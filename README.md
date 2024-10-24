

# **Face Recognition Using YOLOv8 and Facenet**

This project implements a face recognition system that combines **YOLOv8** for face detection and **Facenet** (MTCNN and InceptionResnetV1) for face recognition. It can be used for both live video feeds (e.g., webcam) and static images in a directory structure for building known face embeddings.

## **Features**

- **YOLOv8** for face detection.
- **MTCNN** for accurate face alignment and **InceptionResnetV1** for face embedding extraction.
- Compare face embeddings to recognize known individuals with a specified threshold.
- Save and load known face embeddings for efficient recognition.
- Ability to process and extract embeddings from a directory structure containing images.

## **Installation**

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/face-recognition-yolov8-facenet.git
   cd face-recognition-yolov8-facenet
   ```

2. **Install Dependencies**

   You can install the required Python packages using `pip`:
   ```bash
   pip install -r requirements.txt
   ```

   **Main dependencies include**:
   - OpenCV (`cv2`)
   - Facenet-PyTorch (MTCNN and InceptionResnetV1)
   - Ultralytics (`YOLOv8` model)
   - NumPy
   - Pickle (for saving/loading embeddings)

3. **Download YOLOv8 Model**
   
   Download the pre-trained YOLOv8 weights and save it in the `detection/weights/` directory.

## **Usage**

### **1. Real-Time Face Recognition (Webcam)**

You can run the script for real-time face recognition using the webcam by executing:

```bash
python face_recognition_webcam.py
```

The system will:
- Detect faces using YOLOv8.
- Extract embeddings using MTCNN and InceptionResnetV1.
- Compare embeddings with pre-saved known face embeddings and display the recognized faces.

### **2. Embedding Generation from a Directory**

To generate and save embeddings from a directory containing labeled subfolders of images:

```bash
python save_embeddings.py
```

Ensure the directory structure is like:

```
known_faces/
├── person1_name/
│   ├── img1.jpg
│   ├── img2.jpg
│   └── ...
├── person2_name/
│   ├── img1.jpg
│   ├── img2.jpg
│   └── ...
└── ...
```

After processing, embeddings will be saved to `known_embeddings.pkl`.

### **3. Adjusting Recognition Threshold**

The default threshold for recognizing a face is 0.2. You can adjust this by modifying the `compare_embeddings` function in `face_recognition_webcam.py`.

## **Files**

- **face_recognition_webcam.py**: Script for real-time face recognition using a webcam.
- **save_embeddings.py**: Script for generating and saving face embeddings from images.
- **known_embeddings.pkl**: Pre-saved face embeddings.
- **detection/weights/best.pt**: YOLOv8 pre-trained model weights for face detection.

## **License**

This project is licensed under the **MIT License**.


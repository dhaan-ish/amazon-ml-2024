# Amazon ML Challenge: Entity Extraction from Product Images

## **Introduction**

This project was developed as part of the Amazon ML Challenge to create a machine learning solution capable of extracting entity values from product images. Extracting precise product information such as weight, volume, and dimensions is vital for applications in e-commerce, healthcare, and content moderation.

---

## **Approach Overview**

Our hybrid approach integrates Optical Character Recognition (OCR), image processing, and machine learning techniques to extract entity names and values directly from images.

### **Workflow:**

1. **OCR-Based Text Extraction**: Used PaddleOCR for extracting text from images.
2. **Regex-Based Entity Extraction**: Designed regex patterns for entity-specific values, refined through manual evaluation.
3. **Image Processing for Dimensions**: Leveraged OpenCV for line detection and KNN for associating dimensional attributes like width, depth, and height.
4. **Class-Specific Evaluation**: Split the test dataset by entity class for optimized performance and accuracy.

---

## **Methodology**

### **1. OCR with PaddleOCR**

- Selected for its high accuracy with structured text, ideal for product labels.

### **2. Regular Expression Extraction**

- Fine-tuned regex patterns for entities like:
    - **Weight**: e.g., **`r'(\d+(\.\d+)?\s*(gram|kilogram|ounce|pound))'`**
    - **Voltage**: e.g., **`r'(\d+(\.\d+)?\s*(volt|kilovolt|millivolt))'`**
- Patterns were validated across hundreds of images to handle diverse formats.

### **3. Dimensional Extraction (Width, Depth, Height)**

- Detected horizontal and vertical lines using OpenCV.
- Applied KNN to match nearest text to lines, identifying dimensional attributes.
- Used PaddleOCR and regex for extracting numerical values and units.

### **4. Dataset Splitting for Specialized Models**

- Divided test data into 8 subsets based on entity classes for targeted evaluation and submission.

---

## **Challenges & Solutions**

1. **Dimensional Extraction**: Combined OpenCV and KNN for accurate association of text with labels.
2. **Regex Design**: Created robust patterns by manually analyzing diverse data formats.

---

## **Results**

Our model was evaluated using the F1 score. The combination of PaddleOCR, regex-based extraction, and image processing provided accurate results, particularly for weight, volume, and dimensions.

We achieved 60 F1 score at last.

---

## **Conclusion**

This project demonstrates the effectiveness of combining OCR, regex-based techniques, and image processing for extracting structured information from images. The class-specific approach ensured scalability and accuracy across varied datasets.

---

### **Tech Stack**

- **PaddleOCR**
- **OpenCV**
- **KNN Algorithm**
- **Regular Expressions (Regex)**

---

Feel free to explore the repository for more details on the implementation!
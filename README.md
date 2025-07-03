
# Face Recognition Theft Detection System

## 🛡️ Project Overview

The **Face Recognition Theft Detection System** is a real-time surveillance application designed to automatically identify and flag known shoplifters using facial recognition technology. It leverages computer vision to scan video feed from a webcam, detect faces, match them against a database of known offenders, and trigger alerts when a match is found.

The system is optimized for environments like retail stores, warehouses, libraries, or any place where monitoring known individuals is crucial. By preloading only the faces of shoplifters into the database, the system ensures **privacy-first recognition**, meaning only flagged individuals are identified — all others remain anonymous.

## 🎯 Key Features

### ✅ Real-Time Face Detection
- Continuously processes live webcam footage.
- Detects and tracks all visible faces in each video frame.

### 🔴 Shoplifter Identification
- Matches detected faces against a database of **known shoplifters only**.
- If a match is found, highlights the person with a **red box** and a warning label.
- All others are ignored — no unnecessary recognition or storage.

### 🎥 Automatic Video Recording
- Saves **10 seconds of footage before and after** a shoplifter is detected.
- Ensures evidence includes full context of the incident.
- Videos are saved locally in a dedicated folder with a timestamp.

### ⚙️ Customizable Thresholds
- Adjustable face match sensitivity (confidence threshold).
- Easy to add or remove shoplifters by updating image files.

### 📁 Organized Folder Structure
- `shoplifters/`: where you store all images of flagged individuals.
- `theft_footage/`: automatically stores saved video evidence.
- `encodings.pkl`: file storing facial features for faster recognition.
- Scripts: to generate encodings and run the main detection system.

## 💡 How It Works (Behind the Scenes)

1. **Encoding Phase**:  
   The system first processes the images of known shoplifters using a script that converts each face into a 128-dimensional encoding. This encoding is saved to a file so the detection process can run in real time without reprocessing.

2. **Detection Phase**:  
   When the main detection script runs:
   - It captures video from a webcam.
   - Detects all faces and encodes them in real time.
   - Compares each detected face to the preloaded encodings.
   - If a match exceeds the confidence threshold, it triggers an event.

3. **Event Handling**:  
   Upon recognizing a shoplifter:
   - The system starts recording video footage.
   - It writes the **10 seconds leading up to the detection** (using a rolling buffer).
   - Then continues recording for **10 seconds after**.
   - The video is saved to the local disk for evidence.

## 🔐 Privacy-First Design

Unlike general facial recognition systems, this one **only recognizes people who have already been flagged** (e.g., known shoplifters). It does not:
- Store or track the general public.
- Upload or transmit any video data to external services.
- Perform surveillance beyond its defined scope.

This makes it ideal for use in ethical surveillance systems.

## 🧰 Use Cases

- 🏬 **Retail stores** to flag repeat offenders.
- 🏗️ **Warehouses** to monitor restricted zones.
- 📚 **Libraries** for detecting banned individuals.
- 🏢 **Office spaces** with entry restrictions.

## 🔄 Customization Options

- Update the **shoplifter list** by adding/removing images.
- Adjust **face recognition strictness** for higher or lower tolerance.
- Configure output folder, video format, and duration of saved clips.
- Extend functionality to include:
  - Cloud uploads (e.g., Google Drive, AWS S3)
  - Notification alerts via email or SMS
  - A SaaS dashboard for centralized monitoring


## Setup Instructions

### 1. Prepare Known Faces
- Add images of known shoplifters to the `known_faces/` folder.
- Images should be clear and contain one face each, named by the person’s identifier (e.g., `john_doe.jpg`).

### 2. Generate Face Encodings
- Run the `encode_faces.py` script to process the images and create `encodings.pkl`.
- This pickle file contains the facial encodings and corresponding names used for recognition.

### 3. Install Dependencies
- Create a Python virtual environment (recommended).
- Install required packages from `requirements.txt`:
  ```bash
  pip install -r requirements.txt



## 📌 Why This Project?

This project solves a real-world problem by combining:
- The power of AI (face recognition)
- Real-time video processing
- A privacy-conscious approach

It’s especially helpful for security teams or small businesses that want to **automate threat detection** using inexpensive hardware like webcams and local machines — no complex infrastructure required.

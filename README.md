# Python-computer-vision-project
face-recognition-attendance-system
AI-Powered Biometric Attendance System
A real-time face recognition application built with OpenCV and Dlib’s Deep Learning-based face encodings. This system automates attendance logging by identifying individuals from a live video stream and recording their entry in a structured CSV format.

- Key Features
Real-time Recognition: Identifies multiple faces simultaneously using a webcam feed.

Daily Log Automation: Automatically generates a new CSV file every day (e.g., 2026-03-23.csv) to keep data organized.

Performance Optimization: Implements frame resizing (0.25x) to reduce computational load and increase FPS (Frames Per Second).

Duplicate Prevention: Logic ensures each person is logged only once per session, even if they remain in front of the camera.

Visual Feedback: Overlays real-time "Present" labels on the video feed for verified users.

🛠️ Tech Stack
Language: Python

Computer Vision: OpenCV (cv2)

Deep Learning: face_recognition (utilizing a pre-trained ResNet-model for 128-d encodings)

Data Handling: NumPy, CSV, Datetime

📊 How It Works (The ML Pipeline)
Preprocessing: Each video frame is resized and converted from BGR to RGB (OpenCV defaults to BGR, but face_recognition requires RGB).

Face Encoding: The system extracts unique 128-d vector embeddings for every face detected in the frame.

Vector Comparison: Using Euclidean Distance, the system compares the live encoding against a database of "Known Encodings."

Thresholding: If the smallest distance is below a specific threshold (typically 0.6), a match is confirmed.


1. Install Dependencies:


pip install face_recognition opencv-python numpy
2. Setup Images:
Place .jpeg or .png files of the users in the faces/ folder. Ensure the filename matches the name you want to appear in the logs.

3. Run the System:
python main.py

📈 Future Improvements
Database Integration: Migrate from CSV to SQLite or MongoDB for scalability.

Anti-Spoofing: Implement liveness detection to prevent "photo-based" attendance fraud.

Cloud Logging: Sync logs to a cloud dashboard for remote monitoring.


# Face Recognition Attendance System

A secure face recognition attendance system built with Python for automated attendance marking, user enrollment, and administrative management. The project uses DeepFace for facial embeddings, OpenCV for image capture and liveness checks, Flask for backend APIs, SQLite for data storage, and CustomTkinter for the admin dashboard.

---

## Features

- Face-based attendance marking  
- User enrollment using webcam  
- Admin dashboard for managing users and viewing logs  
- Blink-based liveness detection (anti-spoofing)  
- Encrypted storage of face embeddings  
- Hashed admin credentials  
- Attendance logging with timestamps  
- Email alerts for after-hours attendance  
- Maintenance mode for safe camera switching  

---

## Tech Stack

- **Language:** Python  
- **Backend:** Flask, SQLite  
- **Computer Vision:** OpenCV, DeepFace (FaceNet512)  
- **GUI:** CustomTkinter  
- **Security:** Cryptography (Fernet), Werkzeug  
- **Other:** NumPy, Pillow, Requests  

---

## Project Structure

```
face-recognition-attendance-system/
│
├── server.py               # Backend API and core logic
├── admindashboard.py       # Admin dashboard (GUI)
├── attendance_client.py    # Attendance kiosk client
├── enrollment_client.py    # Enrollment client
├── README.md               # Documentation
```

---

## How It Works

1. The server initializes the database and loads stored facial embeddings.  
2. Admin logs in via dashboard to enroll users and manage records.  
3. The attendance client captures a face and performs blink-based liveness detection.  
4. The image is sent to the server for recognition.  
5. If matched, attendance is recorded; otherwise, user is marked unknown.  
6. If attendance occurs outside office hours, an email alert is triggered.  

---

## Setup Instructions

### 1. Install Dependencies
```bash
pip install flask flask-cors deepface opencv-python cryptography requests pillow werkzeug customtkinter numpy
```

### 2. Run the Server
```bash
python server.py
```

### 3. Run Admin Dashboard
```bash
python admindashboard.py
```

### 4. Run Attendance Client
```bash
python attendance_client.py
```

---

## Default Credentials

```
Username: admin  
Password: admin123  
```

⚠️ Change these credentials before using in a real environment.

---

## Configuration

Update the following in `server.py` before running:

- Email credentials (for alerts)
- Encryption key
- Office hours
- Admin email

---

## Notes

- Ensure only one application is accessing the camera at a time  
- Good lighting improves face detection accuracy  
- System is designed for local/demo usage  

---

## Future Improvements

- Environment variable configuration  
- Advanced anti-spoofing techniques  
- Cloud database integration  
- Role-based access control  
- Attendance analytics dashboard  

---

## License

This project is for educational purposes.

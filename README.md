# Face Recognition Based Attendance System

A Python-based attendance system that uses face recognition technology to automatically mark attendance for registered users.

## Features

- **Face Recognition**: Uses OpenCV and scikit-learn for accurate face detection and recognition
- **Web Interface**: Flask-based web application with a user-friendly interface
- **Automatic Attendance**: Captures attendance automatically when a registered face is detected
- **User Management**: Add new users and manage existing registrations
- **Attendance Reports**: View daily attendance records in CSV format
- **Real-time Processing**: Live video feed with real-time face detection

## Technologies Used

- **Python 3.x**
- **Flask** - Web framework
- **OpenCV** - Computer vision and image processing
- **scikit-learn** - Machine learning (K-Nearest Neighbors classifier)
- **Pandas** - Data manipulation and CSV handling
- **NumPy** - Numerical computing
- **Joblib** - Model persistence

## Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd face-recognition-based-attendance-system
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   python app.py
   ```

4. **Access the application**
   Open your web browser and go to `http://localhost:5000`

## Usage

### Adding New Users
1. Go to the home page
2. Enter the user's name and roll number
3. Click "Add New User"
4. The system will capture 10 images of the user's face
5. The model will be automatically trained with the new data

### Taking Attendance
1. Click "Take Attendance" on the home page
2. The webcam will activate and start detecting faces
3. When a registered face is detected, attendance is automatically marked
4. Press 'ESC' to stop the attendance process

### Viewing Attendance
- The home page displays today's attendance records
- Attendance is saved in CSV format in the `Attendance/` folder
- Each day has a separate attendance file

### Managing Users
- Go to "List Users" to see all registered users
- Delete users if needed (this will retrain the model)

## Project Structure

```
face-recognition-based-attendance-system/
├── app.py                          # Main Flask application
├── haarcascade_frontalface_default.xml  # Face detection model
├── requirements.txt                # Python dependencies
├── README.md                      # Project documentation
├── templates/                     # HTML templates
│   └── home.html                 # Main web interface
├── static/                       # Static files
│   └── faces/                    # User face images (auto-created)
└── Attendance/                   # Attendance CSV files (auto-created)
```

## How It Works

1. **Face Detection**: Uses Haar Cascade classifier to detect faces in video frames
2. **Feature Extraction**: Extracts face features and resizes images to 50x50 pixels
3. **Training**: Uses K-Nearest Neighbors algorithm to train on user face data
4. **Recognition**: Compares detected faces with trained data to identify users
5. **Attendance Marking**: Automatically records attendance with timestamp

## Requirements

- Python 3.7 or higher
- Webcam for face capture and recognition
- Good lighting conditions for better face detection accuracy

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- OpenCV community for face detection algorithms
- scikit-learn for machine learning capabilities
- Flask framework for web development

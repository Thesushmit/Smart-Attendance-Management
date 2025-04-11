Certainly! Here's a comprehensive `README.md` file tailored for the [Smart-Attendance-Management](https://github.com/Thesushmit/Smart-Attendance-Management) project.

---

# Smart Attendance Management System

A real-time, AI-powered attendance system that leverages facial recognition and mask detection to automate attendance tracking. Built with Python, OpenCV, YOLOv5, and FaceNet, this system ensures accurate and efficient attendance management.

## 📌 Features

- **Real-Time Face Recognition**:Utilizes MTCNN for face detection and FaceNet for face recognition
- **Mask Detection**:Integrates YOLOv5 to detect mask status—`with_mask`, `without_mask`, or `mask_weared_incorrect`
- **Automated Attendance Logging**:Records attendance in an Excel file (`attendance.xlsx`) with details like subject, entry time, mask status, punctuality, and date
- **Timetable Integration**:Determines the current subject based on a predefined timetable
- **User-Friendly Interface**:Provides a command-line interface for taking attendance, clearing records, and adding new students

## 🗂️ Directory Structure

``
Smart-Attendance-Management/
├── known_faces/
│   ├── person1/
│   │   ├── photo1.jpg
│   │   ├── photo2.jpg
│   │   └── ...
│   └── person2/
│       ├── photo1.jpg
│       └── ...
├── attendance.xlsx
├── last.pt
├── main.py
└── README.md
``


- **`known_faces/`** Directory containing subfolders for each person, with their respective image.
- **`attendance.xlsx`** Excel file where attendance records are store.
- **`last.pt`** Pre-trained YOLOv5 model for mask detectio.
- **`main.py`** Main script to run the attendance syste.

## 🚀 Installation

1. **Clone the Repository**

   ``bash
   git clone https://github.com/Thesushmit/Smart-Attendance-Management.git
   cd Smart-Attendance-Management
   ``


2. **Create a Virtual Environment (Optional but Recommended)**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ``


3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ``

4. **Download YOLOv5 Model**

   Place the `last.pt` YOLOv5 model file in the project root directory. Ensure it's trained for mask detection.

## 🧑‍🎓 Adding New Students

1. **Run the Script**

   ``bash
   python main.py
  ``


2. **Select Option to Add New Student**

   Follow the on-screen instructions to add a new student. A new folder will be created in `known_faces/` with the student's name.

3. **Add Photos**

   Place at least 5 clear photos of the student (with and without a mask) in their respective folder.

## 📅 Timetable Configuraion

The system uses a predefined timetable to determine the current subject based on the day andtim.


```python
TIMETABLE = {
    'Monday': [(9, 'OS'), (10, 'OS'), (11, 'ML'), (12, 'Lunch'), (13, 'CN'), (14, 'CN'), (15, 'ML')],
    'Tuesday': [(9, 'CN'), (10, 'CN'), (11, 'OS'), (12, 'Lunch'), (13, 'ML'), (14, 'ML'), (15, 'OS')],
    'Wednesday': [(9, 'ML'), (10, 'ML'), (11, 'OS'), (12, 'Lunch'), (13, 'CN'), (14, 'CN'), (15, 'Project')],
    'Thursday': [(9, 'OS'), (10, 'CN'), (11, 'ML'), (12, 'Lunch'), (13, 'Project'), (14, 'Project'), (15, 'Library')],
    'Friday': [(9, 'CN'), (10, 'OS'), (11, 'ML'), (12, 'Lunch'), (13, 'Project'), (14, 'ML'), (15, 'OS')]

```


Modify this dictionary in `main.py` to match your institution's schdule.

## 📊 Attendance Loging

Attendance records are stored in `attendance.xlsx` with the following clumns:

- **Subjct**: Current subject based on the timtable.
- **Entry Tme**: Time when the student was reconized.
- **Attendace**: `Present` or `Asent`.
- **Msk**: Mask status (`with_mask`, `without_mask`, or `mask_weared_incorect`).
- **On Tme**: Indicates if the student was on time (`Yes` or`No`).
- **Person Nme**: Recognized name of the sudent.
- **Dte**: Date of the attedance.

## 🛠️ Dependenies

- Pyton 36+
-OpeCV
-Toch
-Pandas
-FacenetPyToch
-Yolovv5
-openyxl

Install all dependencie usng:


```bash
pip install -r requirements.xt
```


## 📌 Notes

- Ensure that the `known_faces/` directory is structured correctly with subfolders for each person 

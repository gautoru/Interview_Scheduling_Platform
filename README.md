# Interview Scheduling Platform

This web application is designed to simplify and streamline the process of scheduling, managing, and updating interviews. The platform provides functionalities for managing users, scheduling interviews, and editing or deleting records as needed.

## Features

### User Management
- Add new users with roles such as **Recruiter**, **Interviewer**, or **Candidate**.
- View a list of all users.
- Edit user information.
- Delete users from the system.

### Interview Scheduling
- Schedule interviews by selecting a date, time, interview type, and the user involved.
- View all scheduled interviews with details like date, time, type, user name, and status.

### Interview Management
- Edit interview details, including rescheduling and changing participants or interview types.
- Delete interviews if no longer needed.

### Navigation
- User-friendly navigation links between different pages such as:
  - **Home**: Add users and navigate to other functionalities.
  - **Schedule Interview**: Schedule a new interview.
  - **Manage Users**: View, edit, or delete users.
  - **Scheduled Interviews**: View all interviews with options to edit or delete.

## Technologies Used

### Backend
- **Flask**: For handling HTTP requests and application logic.
- **MySQL**: For database management.

### Frontend
- **HTML5**: For structuring web pages.
- **CSS3**: For styling.
- **Jinja2 Templates**: For rendering dynamic content.

### Database Structure
1. **User Table**
   - Fields: `UserID`, `Name`, `Email`, `Role`, `Password`, `ContactInfo`
2. **Interview Table**
   - Fields: `InterviewID`, `InterviewType`, `Status`
3. **Schedule Table**
   - Fields: `ScheduleID`, `Date`, `Time`, `InterviewID`, `UserID`

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/<your-username>/interview-scheduling-platform.git
   cd interview-scheduling-platform

CREATE DATABASE InterviewSchedulingPlatform;
USE InterviewSchedulingPlatform;

-- Create User table
CREATE TABLE User (
    UserID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(255),
    Email VARCHAR(255),
    Role VARCHAR(50),
    Password VARCHAR(255),
    ContactInfo VARCHAR(255)
);

-- Create Interview table
CREATE TABLE Interview (
    InterviewID INT AUTO_INCREMENT PRIMARY KEY,
    InterviewType VARCHAR(50),
    Status VARCHAR(50)
);

-- Create Schedule table
CREATE TABLE Schedule (
    ScheduleID INT AUTO_INCREMENT PRIMARY KEY,
    Date DATE,
    Time TIME,
    InterviewID INT,
    UserID INT,
    FOREIGN KEY (InterviewID) REFERENCES Interview(InterviewID),
    FOREIGN KEY (UserID) REFERENCES User(UserID)
);
to run the application
python app.py

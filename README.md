# Navadaya Girls Hostel Management System

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/flask-%23000.svg?style=flat&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![Firebase](https://img.shields.io/badge/firebase-%23039BE5.svg?style=flat&logo=firebase)](https://firebase.google.com/)

> A comprehensive digital solution for managing Girls Hostel operations with cutting-edge security features and real-time management capabilities.

## 🏨 Overview

The Navadaya Girls Hostel Management System is a modern web-based platform designed to streamline administrative processes and enhance student experience through innovative digital solutions. Built with a robust architecture combining Flask backend and Firebase real-time database, this system offers comprehensive tools for hostel administration.

### ✨ Key Features

- **🔐 Advanced Authentication System**
  - Firebase-based secure login with Google integration
  - Role-based access control (Admin/Student portals)
  - Session management and security monitoring

- **👥 Student Management**
  - Complete student registration and profile management
  - Academic information tracking
  - Contact details and emergency contacts

- **🏠 Room Management** 
  - Room allocation and occupancy tracking
  - Maintenance request management
  - Room change request processing

- **💰 Fee Management**
  - Digital fee collection and tracking
  - Receipt generation with QR code verification
  - Payment history and due management

- **📢 Communication System**
  - Notice board for announcements
  - Complaint management system
  - Real-time notifications

- **📊 Advanced Reporting**
  - Student reports with detailed analytics
  - Fee collection reports
  - Custom PDF generation with security features

- **🔒 Enhanced Security Features**
  - QR code-based receipt verification system
  - Advanced cryptographic hashing for tamper detection
  - Multi-parameter security validation
  - Anti-forgery digital signatures

## 🚀 Quick Start

### Prerequisites

- Python 3.11 or higher
- Node.js (for development tools)
- Firebase account and project setup

### Installation

1. **Clone the repository**
   ```bash
   https://github.com/sushilcodex01/Hostel-Management-System.git
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Firebase**
   - Update `js/firebase-config.js` with your Firebase project credentials
   - Set up Firebase Authentication and Firestore database
   - Configure security rules using `firebase-security-rules.txt`

4. **Run the application**
   ```bash
   # Using Flask (recommended for development)
   python main.py
   
   # Or using the simple server
   python server.py
   ```

5. **Access the application**
   - Admin Portal: `http://localhost:5000`
   - Student Portal: `http://localhost:5000/student-portal.html`

## 🏗️ Architecture

### Frontend
- **Technology**: Vanilla JavaScript, HTML5, CSS3
- **Architecture**: Multi-Page Application (MPA)
- **UI Framework**: Custom responsive design with Font Awesome icons
- **Authentication**: Firebase Auth integration

### Backend
- **API Framework**: Flask (Python)
- **Database**: Firebase Firestore (NoSQL)
- **File Storage**: Firebase Storage
- **PDF Generation**: ReportLab library
- **Security**: QR codes with PIL and custom hashing

### Project Structure
```
navadaya-hostel-management/
├── main.py                     # Flask API server
├── server.py                   # Development static server
├── index.html                  # Admin login page
├── dashboard.html              # Admin dashboard
├── student-portal.html         # Student interface
├── css/
│   └── styles.css             # Main stylesheet
├── js/
│   ├── auth.js                # Authentication module
│   ├── firebase-config.js     # Firebase configuration
│   ├── dashboard.js           # Dashboard functionality
│   ├── students.js            # Student management
│   ├── rooms.js               # Room management
│   ├── fees.js                # Fee management
│   ├── notices.js             # Notice management
│   ├── complaints.js          # Complaint system
│   ├── reports.js             # Report generation
│   └── utils.js               # Utility functions
├── complaints.html             # Complaint management
├── fees.html                   # Fee management
├── notices.html                # Notice board
├── rooms.html                  # Room management
├── students.html               # Student management
├── receipt-verification.html   # Security verification
├── leavemanagement.html        # Leave requests
├── roomchangemanagement.html   # Room change requests
└── roommaintenancerequests.html # Maintenance tracking
```

## 📱 Features Overview

### Admin Portal
- **Dashboard**: Overview of key metrics and recent activities
- **Student Management**: Add, edit, and manage student records
- **Room Management**: Allocate rooms and track occupancy
- **Fee Management**: Process payments and generate receipts
- **Notice Board**: Create and manage announcements
- **Complaint System**: Track and resolve student complaints
- **Reports**: Generate comprehensive reports and analytics
- **Receipt Verification**: Advanced security verification system

### Student Portal
- **Profile Management**: View and update personal information
- **Fee Payment**: Make payments and download receipts
- **Room Information**: View current room details
- **Notices**: Read hostel announcements
- **Complaints**: Submit and track complaint status
- **Leave Requests**: Apply for leave permissions

## 🔒 Security Features

### Advanced Receipt Security System
- **Multi-Parameter Verification**: Uses fee ID, roll number, amount, and timestamp
- **Cryptographic Hashing**: Advanced security hash generation for tamper detection
- **QR Code Integration**: Secure QR codes with embedded verification data
- **Admin Verification Portal**: Real-time receipt authentication system
- **Anti-Forgery Protection**: Digital signatures and tamper-evident design

### Authentication & Authorization
- **Firebase Authentication**: Industry-standard secure authentication
- **Role-Based Access**: Separate admin and student access levels
- **Session Management**: Secure session handling and timeout
- **Google Integration**: Optional Google Sign-In for convenience

## 🛠️ API Endpoints

### Report Generation
```bash
POST /api/generate-student-report    # Generate student reports
POST /api/generate-fees-report       # Generate fee collection reports
POST /api/generate-receipt           # Generate secure payment receipts
```

### File Serving
```bash
GET /                               # Serve admin login page
GET /<path>                         # Serve static files
```

## 🔧 Configuration

### Firebase Setup
1. Create a new Firebase project
2. Enable Authentication and Firestore
3. Update `js/firebase-config.js` with your project credentials:
   ```javascript
   const config = {
       apiKey: "your-api-key",
       authDomain: "your-project.firebaseapp.com",
       projectId: "your-project-id",
       // ... other config
   };
   ```

### Security Rules
Apply the Firestore security rules from `firebase-security-rules.txt` to ensure proper data access control.

## 🚀 Deployment

### Replit Deployment (Recommended)
1. Fork this repository on Replit
2. Configure environment variables
3. Run the application using the built-in runner

### Manual Deployment
1. Set up a Python web server (Gunicorn recommended)
2. Configure environment variables for production
3. Set up Firebase hosting for static assets (optional)
4. Configure domain and SSL certificates

## 📊 Database Schema

### Students Collection
```javascript
{
  studentId: "unique-id",
  personalInfo: { name, rollNumber, email, phone },
  academicInfo: { course, year, department },
  roomInfo: { roomNumber, allocationDate },
  emergencyContact: { name, phone, relation }
}
```

### Fees Collection
```javascript
{
  feeId: "unique-id",
  studentId: "reference",
  amount: number,
  feeType: "string",
  paymentDate: "timestamp",
  status: "paid/pending",
  receiptData: { verificationCode, securityHash }
}
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines
- Follow Python PEP 8 style guidelines
- Use meaningful commit messages
- Add comments for complex functionality
- Test thoroughly before submitting

## 📋 Requirements

### Python Dependencies
```
flask>=3.1.1
pillow>=11.3.0
qrcode[pil]>=8.2
reportlab>=4.4.3
requests>=2.32.4
twilio>=9.7.0
```

### Frontend Dependencies
- Firebase SDK (loaded via CDN)
- Font Awesome Icons
- Google Fonts (Inter)

## 🐛 Known Issues

- Firebase authentication may require page refresh on first load
- PDF generation requires sufficient server memory for large reports
- QR code verification requires stable internet connection

## 📞 Support

For support and questions:
- Create an issue on GitHub
- Check the documentation in `replit.md`
- Review the Firebase console for authentication issues

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Firebase team for robust backend services
- ReportLab contributors for PDF generation capabilities
- Font Awesome for comprehensive icon library
- Google Fonts for typography

---

**Made with ❤️ for modern hostel management**

> **Note**: This system is designed for educational institutions and can be customized for different hostel management needs. For production deployment, ensure proper security configurations and regular backups.

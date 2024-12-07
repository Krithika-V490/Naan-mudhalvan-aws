
# AWS Virtual Classroom

## Overview
This project implements a web-based virtual classroom platform using **Flask** and integrates cloud services from **AWS**. It allows users to securely register, log in, and access course materials hosted on AWS S3. The application is backed by a MySQL database hosted on AWS RDS, ensuring scalability and security.

---

## Features
- **User Registration**: New users can register with a username and password.
- **Secure Login**: Authenticated access to the dashboard using hashed passwords.
- **Course Dashboard**: Access downloadable course materials hosted on AWS S3.
- **AWS Integration**: Utilizes AWS S3 for file storage and AWS RDS for database management.
- **Logout**: Ensures secure session termination.

---

## Technologies Used
### Backend
- Python with Flask
- MySQL Connector for database interactions

### Cloud Services
- **AWS S3**: For storing and delivering course materials.
- **AWS RDS**: For managing the MySQL database.

### Libraries
- `Flask`: Web framework for the application.
- `werkzeug.security`: For password hashing and verification.
- `mysql.connector`: For database connectivity.

---

## Setup and Installation

### Prerequisites
1. Python 3.x installed on your system.
2. AWS account with:
   - An S3 bucket for course materials.
   - An RDS instance for MySQL database.
3. MySQL database with the following schema:

   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       username VARCHAR(255) NOT NULL,
       password_hash VARCHAR(255) NOT NULL
   );
   ```

### Installation Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/aws-virtual-classroom.git
   cd aws-virtual-classroom
   ```
2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```
3. Update the database connection in `app.py`:
   ```python
   def get_db_connection():
       return mysql.connector.connect(
           host='your-rds-endpoint',
           user='your-db-username',
           password='your-db-password',
           database='course_app'
       )
   ```
4. Run the application:
   ```bash
   python app.py
   ```
5. Access the app at `http://localhost:5000`.

---

## Project Structure
```
.
├── templates/            # HTML templates
│   ├── home.html
│   ├── register.html
│   ├── login.html
│   ├── dashboard.html
├── app.py                # Main application logic
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

---

## Future Enhancements
- Add user roles (e.g., admin, student) for better management.
- Implement real-time video classes using AWS Chime SDK.
- Include session management for secure and dynamic user interactions.
- Add analytics to track user activity and course progress.

---

## Security Considerations
- **Password Hashing**: Uses `werkzeug.security` to hash passwords before storing them in the database.
- **AWS IAM**: Manages secure access to AWS resources.
- **Session Management**: Prevents unauthorized access to the dashboard.

---

## License
This project is licensed under the [MIT License](LICENSE).

---

## Contact
For any queries or feedback, please contact:
- Name: Krithika V
- Email: krithikav045@gmail.com

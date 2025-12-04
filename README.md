#  **QuizEngine — A-Level NEA Project**

## 📌 Overview

This project is a fully functional **digital quiz platform** built in **Python** with a **MySQL relational database backend**.
It allows users to create quizzes, take quizzes, store results, and view leaderboards — functioning similarly to platforms like Kahoot but with a Python-driven interface and custom SQL schema.

The system was designed, implemented, and documented as part of my **A-level Computer Science NEA**, demonstrating full-stack development skills including:

* Python programming
* Object-oriented design
* Relational database modelling
* SQL queries and schema design
* User authentication (with salted + hashed passwords)
* Data validation and error handling
* Complex algorithms (randomisation, input validation, dynamic quiz rendering)

The full technical write-up is available in this repository:
📄 *“Computing Practical Project Write-Up”* (see file in repo) 

---

## 🚀 **Features**

### **Quiz Creation**

* Create quizzes with up to 50 questions
* Supports both **multiple-choice** and **open-ended** question types
* Stores quiz metadata (title, description, difficulty, max score)
* Fully normalised MySQL schema (3NF)

### **Quiz Taking**

* Randomised question ordering
* Dynamic multiple-choice answer shuffling
* Automatic scoring
* Robust input validation
* Real-time feedback on answers

### **User Accounts**

* Secure account creation
* Password hashing using **SHA-512 PBKDF2** with unique per-user salts
* Persistent profiles stored in MySQL
* Tracks user scores, quiz attempts, and accumulated points

### **Leaderboards**

* Global leaderboard
* Quiz-specific leaderboards
* Stored entirely in SQL for accuracy + performance

### **Database Design**

Includes:

* 7 fully normalised tables
* Foreign key constraints
* Indexing for performance
* Security considerations
* Sample SQL queries for CRUD operations
  (See full write-up for diagrams and schema details.)

---

## 🛠 **Technologies Used**

| Area         | Tools / Technologies                                  |
| ------------ | ----------------------------------------------------- |
| Programming  | Python 3.9                                            |
| Database     | MySQL Workbench + MySQL Connector                     |
| Security     | PBKDF2-HMAC SHA-512, salted hashing                   |
| Paradigm     | Object-Oriented Programming                           |
| Validation   | Full defensive input validation                       |
| Architecture | Multi-file Python modules interacting with SQL tables |

---

## 📦 **Installation & Setup**

To run this project on your own machine:

### **1️⃣ Install MySQL**

You will need MySQL Server + MySQL Workbench installed.

### **2️⃣ Create a new database**

Open MySQL Workbench and create a schema (e.g., `quiz`).

### **3️⃣ Import the required tables**

Inside this repository, open the folder:

```
SQL Text Files/
```

Run the SQL file:

```
DataBase_relationships_for_my_project.sql
```

This will create all 7 tables and relationships needed to run the system.

### **4️⃣ Run the program**

Ensure the Python script has correct MySQL credentials.
Then run:

```
python main.py
```

You’re ready to begin using the system.

---

## 🎮 **How to Use**

### **1. Create an account**

You will be prompted to create a user with:

* First name
* Last name
* Email
* Password (securely hashed + salted)

### **2. Access the main menu**

From here, you can:

* Take a quiz
* Create a quiz
* Delete your quizzes
* View your profile
* View leaderboards

### **3. Create your own quizzes**

You define:

* Number of questions
* Difficulty
* Free-text or multiple-choice answers
  All data is stored in the MySQL database.

---

## 🧪 **Testing**

The system was thoroughly tested using:

* Normal, erroneous, and boundary inputs
* Validation for all user input paths
* Data integrity tests using SQL
* Manual walkthrough testing
* Automated behaviour verification with expected output tables

Full test plan + evidence are included in the write-up.
See: *Testing* section of the NEA document. 

---

## 🔒 **Security**

Passwords are not stored in plaintext. The system:

* Generates a random salt for each user (`os.urandom(60)`)
* Hashes passwords with PBKDF2-HMAC SHA-512
* Stores salting + hashing results securely in MySQL
* Validates credentials by recomputing hashes

This ensures safe storage even in case of database compromise.

---

## 📚 **Project Documentation**

The full NEA write-up contains:

* Problem definition
* Research and interviews
* System modelling
* Normalised database schema (ER diagrams)
* Flowcharts & structure charts
* Annotated code
* Test plan + evidence
* Evaluation & improvements

You can view the full document here:
📄 *Computing Practical Project Write-Up* (included in repo) 

---

## 💡 **Future Improvements**

If expanded beyond the A-level NEA scope, the project could include:

* GUI (Tkinter or PyQt)
* Web-based version using Flask/Django
* More question types (image, audio, video)
* Improved UX for quiz navigation
* Timed quizzes & streak bonuses
* Email verification + password reset flow

---

## 👤 **Author**

**Isaac Patrickson**
A-level Computer Science NEA (2022)
Now a degree apprentice working toward Level 6 Digital Technology Solutions (Software Engineering)

GitHub: *github.com/IsaacPatrickson*
Email: *[isaacspatrickson@gmail.com](mailto:isaacspatrickson@gmail.com)*

# MINIHELPDESK – PROJECT REPORT

## Submitted To

**Course:** Web Technologies I (CS4717)

## Submitted By

| Student Name         | Student ID |
| -------------------- | ---------- |
| Muhammad Ahmed Taha  | 2312164    |
| Sher Muhammad Simair | 2312178    |

**Section:** BSCS – VIB
**Semester:** Spring 2026

---

# 1. Project Title

## MiniHelpDesk: A Full-Stack Ticket Management System

---

# 2. Abstract

MiniHelpDesk is a web-based ticket management application developed to streamline the process of reporting and managing support requests. The system enables users to create, view, and delete tickets while providing a simple and intuitive user experience.

The project follows a modern full-stack architecture using React and TypeScript for the frontend, Express and Node.js for backend services, and MongoDB for persistent data storage. RESTful APIs facilitate communication between the client and server, ensuring modularity and maintainability.

The application fulfills all mandatory project requirements and includes additional engineering and product features designed to improve usability and prevent common user errors.

---

# 3. Introduction

Organizations often require efficient mechanisms for tracking issues, managing requests, and monitoring support activities. Traditional manual approaches may result in delayed responses, data inconsistency, and poor organization.

MiniHelpDesk addresses these challenges by providing a centralized platform where users can:

* Submit support requests.
* Track existing tickets.
* Remove resolved or unnecessary tickets.
* Manage tickets efficiently through an interactive interface.

The project demonstrates the practical application of full-stack development concepts taught in the Web Technologies I course.

---

# 4. Project Objectives

The primary objectives of this project are:

* To design and develop a complete full-stack web application.
* To implement CRUD-related operations using REST APIs.
* To integrate React frontend applications with Express backend services.
* To utilize MongoDB for persistent data storage.
* To apply TypeScript in both frontend and backend environments.
* To ensure proper validation and error handling mechanisms.
* To enhance usability through additional product and engineering features.

---

# 5. Technologies Used

## 5.1 Frontend Technologies

| Technology       | Purpose                           |
| ---------------- | --------------------------------- |
| React 18         | Building the user interface       |
| TypeScript       | Type safety and maintainability   |
| Vite             | Development server and build tool |
| React Router DOM | Client-side routing               |
| Axios            | API communication                 |
| React Hot Toast  | User notifications                |

---

## 5.2 Backend Technologies

| Technology | Purpose                         |
| ---------- | ------------------------------- |
| Node.js    | JavaScript runtime              |
| Express.js | Backend framework               |
| TypeScript | Static typing                   |
| Mongoose   | MongoDB object modeling         |
| dotenv     | Environment variable management |
| CORS       | Cross-origin resource sharing   |

---

## 5.3 Database Technology

### MongoDB

MongoDB is a NoSQL document-oriented database used to store ticket information.

Benefits include:

* Flexible schema design.
* High scalability.
* Efficient JSON document storage.
* Easy integration with Node.js applications.

---

# 6. System Architecture

The application follows a three-tier architecture.

```
+----------------------+
|      Frontend        |
|  React + TypeScript  |
+----------+-----------+
           |
           | HTTP Requests (Axios)
           |
+----------v-----------+
|       Backend        |
| Express + TypeScript |
+----------+-----------+
           |
           | Mongoose ODM
           |
+----------v-----------+
|      MongoDB         |
|   Ticket Database    |
+----------------------+
```

---

# 7. Project Structure

```
minihelp-desk/

├── frontend/
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   ├── pages/
│   │   └── types/
│   └── .env
│
└── backend/
    ├── src/
    │   ├── controllers/
    │   ├── middleware/
    │   ├── models/
    │   └── routes/
    └── .env
```

---

# 8. Installation Guide

## Step 1: Clone the Repository

```bash
git clone <repository-url>
cd minihelp-desk
```

---

## Step 2: Install Backend Dependencies

```bash
cd backend
npm install
```

---

## Step 3: Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

---

# 9. Environment Configuration

## Backend Environment Variables

Create a `.env` file inside the backend folder.

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/minihelp-desk
```

---

## Frontend Environment Variables

Create a `.env` file inside the frontend folder.

```env
VITE_API_URL=http://localhost:5000
```

---

# 10. MongoDB Configuration

## Local MongoDB Setup

Start MongoDB using:

```bash
mongod
```

Ensure the following connection string exists:

```env
MONGO_URI=mongodb://localhost:27017/minihelp-desk
```

---

## MongoDB Atlas Setup

Replace the local URI with the Atlas connection string.

Example:

```env
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/minihelp-desk
```

---

# 11. Running the Application

## Starting the Backend Server

```bash
cd backend
npm run dev
```

Backend URL:

```
http://localhost:5000
```

---

## Starting the Frontend Application

```bash
cd frontend
npm run dev
```

Frontend URL:

```
http://localhost:5173
```

---

# 12. Ticket Schema

```typescript
{
    subject: string,
    description: string,
    priority: "Low" | "Medium" | "High",
    status: "Open" | "In Progress" | "Closed",
    createdAt: Date
}
```

---

# 13. REST API Endpoints

| Method | Endpoint       | Purpose                  |
| ------ | -------------- | ------------------------ |
| GET    | `/tickets`     | Retrieve all tickets     |
| POST   | `/tickets`     | Create a new ticket      |
| DELETE | `/tickets/:id` | Delete a specific ticket |
| DELETE | `/tickets`     | Delete all tickets       |

---

# 14. Implemented Features

## Mandatory Features

✓ React + TypeScript frontend

✓ Node.js + Express backend

✓ MongoDB database integration

✓ Display all tickets

✓ Create tickets

✓ Delete individual tickets

✓ REST API implementation

✓ Loading indicators

✓ Error handling

✓ Client-side validation

✓ Server-side validation

✓ Proper HTTP status codes

✓ End-to-end integration

---

# 15. Additional Features

## Product Feature (List A)

### Clear All Tickets

The application allows administrators/users to delete all tickets simultaneously.

Implemented functionalities:

* Clear All button.
* Confirmation dialog.
* Warning message before deletion.
* Dedicated DELETE endpoint.
* Automatic interface refresh.
* Success notification displaying deletion statistics.

---

## Engineering Feature (List B)

### Disable Submit While Saving

The application prevents duplicate submissions by temporarily disabling the submit button.

Implemented functionalities:

* Submit button disabled during API requests.
* Dynamic "Saving..." button label.
* Loading spinner.
* Automatic reactivation after completion.
* Duplicate request prevention.

---

# 16. Validation Strategy

## Frontend Validation

The client validates:

* Subject length.
* Description length.
* Required fields.
* Valid priority selection.

---

## Backend Validation

The server validates:

* Data types.
* Required attributes.
* Minimum character requirements.
* Database constraints.

Validation failures return meaningful error messages.

---

# 17. Testing Results

The following functionalities were tested successfully:

| Test Case            | Result |
| -------------------- | ------ |
| Create Ticket        | Passed |
| Retrieve Tickets     | Passed |
| Delete Single Ticket | Passed |
| Delete All Tickets   | Passed |
| Form Validation      | Passed |
| API Error Handling   | Passed |
| Loading States       | Passed |
| MongoDB Integration  | Passed |

---

# 18. Bonus Tasks

No bonus tasks were implemented in this project.

---

# 19. Screenshots

The following screenshots demonstrate the application's functionality:

* Home Interface
* Ticket Creation Form
* Ticket Listing Page
* Delete Confirmation Modal
* Clear All Confirmation Dialog
* Success Notification Messages

**Files Included:**

* 1web.png
* 2.png
* 3.png
* 4.png
* 5.png
* 6.png

---

# 20. Challenges Faced

During development, the team encountered several challenges:

* Establishing communication between frontend and backend.
* Managing TypeScript types across multiple layers.
* Configuring MongoDB connections correctly.
* Preventing duplicate submissions.
* Implementing confirmation dialogs for destructive actions.

These challenges were resolved through testing, debugging, and adherence to best development practices.

---

# 21. Learning Outcomes

Through this project, the team gained practical experience in:

* Full-stack application development.
* RESTful API design.
* MongoDB database integration.
* State management in React.
* TypeScript implementation.
* Error handling techniques.
* Software testing principles.
* Collaborative software development.

---

# 22. Conclusion

MiniHelpDesk successfully demonstrates the implementation of a modern full-stack web application using industry-relevant technologies. The project satisfies all mandatory requirements while incorporating additional features that improve system usability and reliability.

The successful integration of React, Express, TypeScript, and MongoDB highlights the team's understanding of contemporary web development practices and provides a strong foundation for future software engineering projects.


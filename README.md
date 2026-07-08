# Capstone Project Proposal

## Project Title

**Job Tracker Platform**

---

## Project Overview

The Job Tracker Platform is a full-stack web application that helps job seekers search for jobs, save interesting opportunities, and manage their job applications in one place.

### Users will be able to:

- Create an account
- Log in securely
- Search jobs using the Adzuna API
- Save jobs
- Apply to jobs
- Track application status
- Delete saved jobs
- Update application progress

The application will use real-time job listings from the Adzuna API and store user information in MongoDB.

---

## Problem Statement

Many job seekers use several different websites to search for jobs and manually track their applications using spreadsheets or notes. This process is time-consuming and difficult to organize.

The Job Tracker Platform solves this problem by combining job searching and application tracking into one application.

---

## Target Users

- Students
- Software Developers
- Job Seekers
- Career Changers
- New Graduates

---

## Technologies Used

### Frontend

- React.js
- HTML5
- CSS3
- JavaScript
- Axios
- React Router DOM

### Backend

- Node.js
- Express.js

### Database

- MongoDB
- Mongoose

### Authentication

- JWT
- bcrypt

---

## External API

### Adzuna Job Search API

### Base URL

```text
https://api.adzuna.com/v1/api
```

### Job Search Endpoint

```text
https://api.adzuna.com/v1/api/jobs/gb/search/1
```

### Authenticated Request

```text
https://api.adzuna.com/v1/api/jobs/gb/search/1?app_id=YOUR_APP_ID&app_key=YOUR_APP_KEY
```

### Why This API?

The Adzuna API provides real-time job listings from multiple job boards.

The application will allow users to:

- Search jobs by keyword
- Search by location
- View salary information
- View company information
- Open the original job posting

---

## Data Retrieved

- Job Title
- Company Name
- Location
- Salary
- Job Description
- Category
- Contract Type
- Redirect URL
- Posting Date

---

## Features

### User Authentication

- Register
- Login
- Logout
- Secure password encryption

### Job Search

Users can search for jobs such as:

- Software Engineer
- React Developer
- Frontend Developer

### Save Jobs

Users can save jobs for later.

### Application Tracker

Application status includes:

- Saved
- Applied
- Interview
- Offer
- Rejected

### Dashboard

Users can view:

- Saved Jobs
- Applied Jobs
- Interview Jobs
- Favorite Jobs

---

## Database Collections

### Users

```javascript
{
  name,
  email,
  password
}
```

### Saved Jobs

```javascript
{
  userId,
  jobId,
  title,
  company,
  location,
  salary,
  status,
  savedDate
}
```

---

## API Example

### Request

```javascript
axios.get(
  "https://api.adzuna.com/v1/api/jobs/gb/search/1",
  {
    params: {
      app_id: "YOUR_APP_ID",
      app_key: "YOUR_APP_KEY",
      what: "Software Engineer",
      where: "London",
    },
  }
);
```

### Example Response

```json
{
  "title": "Software Engineer",
  "company": {
    "display_name": "Google"
  },
  "location": {
    "display_name": "London"
  },
  "salary_min": 65000,
  "salary_max": 90000,
  "redirect_url": "https://..."
}
```

---

## User Flow

```text
Home Page
    ↓
Register / Login
    ↓
Search Jobs
    ↓
View Job Details
    ↓
Save Job
    ↓
Apply Job
    ↓
Update Status
    ↓
Dashboard
    ↓
Logout
```

---

## Future Enhancements

- Resume Upload
- Email Notifications
- AI Job Recommendations
- Company Reviews
- Interview Notes
- Dark Mode
- Mobile Responsive Design

---

## Project Goals

- Build a full-stack MERN application.
- Integrate the Adzuna REST API.
- Implement secure authentication.
- Store user data in MongoDB.
- Track job applications.
- Build a responsive user interface.

---

## Author

**Jamshed Ali Sher**

Springboard Software Engineering Career Track

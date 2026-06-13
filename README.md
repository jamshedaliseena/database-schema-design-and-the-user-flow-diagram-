Java Script
{
\_id: ObjectId,
username: String,
email: String,
password: String, // hashed with bcrypt
profileImage: String,
createdAt: Date,
updatedAt: Date
}

Applications Collection
{
\_id: ObjectId,

userId: ObjectId, // references Users

companyName: String,
jobTitle: String,
location: String,
salary: Number,

applicationDate: Date,

status: {
type: String,
enum: [
"Applied",
"Interview Scheduled",
"Assessment",
"Rejected",
"Offer Received"
]
},

recruiterName: String,
recruiterEmail: String,

notes: String,

resumeFile: String,
coverLetterFile: String,

createdAt: Date,
updatedAt: Date
}

Saved Jobs Collection (Optional API Integration Feature)

{
\_id: ObjectId,

userId: ObjectId,

companyName: String,
jobTitle: String,
location: String,
jobUrl: String,

savedAt: Date
}

Entity Relationship Diagram (ERD)
┌─────────────────┐
│ USERS │
├─────────────────┤
│ \_id │
│ username │
│ email │
│ password │
│ profileImage │
└────────┬────────┘
│ 1
│
│
│ N
┌────────▼────────┐
│ APPLICATIONS │
├─────────────────┤
│ \_id │
│ userId │
│ companyName │
│ jobTitle │
│ salary │
│ location │
│ status │
│ recruiterName │
│ recruiterEmail │
│ notes │
│ resumeFile │
│ coverLetterFile │
└─────────────────┘

         │
         │ 1
         │
         │ N

┌────────▼────────┐
│ SAVED JOBS │
├─────────────────┤
│ \_id │
│ userId │
│ companyName │
│ jobTitle │
│ jobUrl │
└─────────────────┘

User Flow Diagram
START
|
v
Landing Page
|
+------------------+
| |
v v
Register Login
| |
+--------+---------+
|
v
Dashboard
|
+--------+---------+
| | |
v v v
Add Job View Jobs Search Jobs API
| | |
| | |
v v v
Save Job Edit Job Save External Job
| | |
+--------+---------+
|
v
Application Details
|
v
Update Status
(Applied/Interview/
Assessment/Offer/
Rejected)
|
v
Dashboard Analytics
|
v
Logout

API Routes
Authentication
POST /api/auth/register
POST /api/auth/login
GET /api/auth/profile

Applications
GET /api/applications
POST /api/applications
GET /api/applications/:id
PUT /api/applications/:id
DELETE /api/applications/:id

File Uploads
POST /api/upload/resume
POST /api/upload/coverletter

Jobs API
GET /api/jobs/search

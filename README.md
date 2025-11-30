# Singularium_Internship_Assignment_2025_repo
This repository contains a full-stack solution for the Software Development Intern Assignment by Singularium. The project implements an intelligent Task Priority Analyzer using Django (Backend) and HTML/CSS/JavaScript (Frontend).

The system analyzes tasks based on multiple factors such as urgency, importance, effort, and dependencies, and provides sorted results with computed priority scores.

📌 Features
✅ Backend (Django + REST Framework)

API to analyze and score tasks

Supports 4 scoring modes:

Smart Balance (default)

Fastest Wins

High Impact

Deadline Driven

Circular-dependency-safe scoring logic

Modular architecture (models, serializers, scoring engine, views)

Unit tests for scoring algorithm

Clean REST API responses

✅ Frontend (HTML + CSS + JS)

Paste JSON input for tasks

Select scoring mode

Call backend API and display results

Clean UI and responsive layout

✅ Project Ready for GitHub Review

Full commit history

README with instructions

Requirements.txt

Frontend + Backend separated

Clear code structure

📁 Project Structure
Singularium_Internship_Assignment_2025/
│
├── backend/
│   ├── manage.py
│   ├── requirements.txt
│   ├── task_analyzer/
│   ├── tasks/
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── scoring.py
│   │   ├── views.py
│   │   ├── tests.py
│   │   └── urls.py
│
├── frontend/
│   ├── index.html
│   ├── styles.css
│   └── script.js
│
├── README.md
└── create_commits.sh

⚙️ Setup Instructions — Backend (Django)
1️⃣ Create Virtual Environment
cd backend
python3 -m venv venv
source venv/bin/activate

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Apply Migrations
python manage.py migrate

4️⃣ Run the Server
python manage.py runserver


Server runs on:

🔗 http://127.0.0.1:8000/


API root: /api/tasks/

🖥️ Frontend Setup

No installation needed.

From the frontend folder:

cd frontend
xdg-open index.html


Or open manually in browser.

🔥 API Endpoints
1️⃣ Analyze Tasks

POST /api/tasks/analyze/?mode=smart

Example cURL:
curl -X POST "http://127.0.0.1:8000/api/tasks/analyze/?mode=smart" \
-H "Content-Type: application/json" \
-d '[
  {
    "title": "Fix bug",
    "due_date": "2025-12-01",
    "estimated_hours": 3,
    "importance": 8,
    "dependencies": []
  }
]'

2️⃣ Get Suggestions

GET /api/tasks/suggest/

(Currently placeholder — ready for extension)

🧠 Scoring Algorithm (Summary)

The algorithm evaluates tasks using:

Urgency: How soon the due date is

Importance: User-defined (1–10 scale)

Effort: Lower effort tasks get slight advantage

Dependencies: Tasks blocking others get boosted

Modes:
Mode	Description
Smart Balance	Balanced weighting of all factors
Fastest Wins	Prioritizes low-effort tasks
High Impact	Focuses on high-importance tasks
Deadline Driven	Focuses on urgency
🧪 Unit Tests

Inside backend/tasks/tests.py:

python manage.py test


Covers:

Scoring algorithm

Basic scoring behavior

🧩 Design Decisions

Used Django REST Framework for clean API development

Score calculation is encapsulated in scoring.py

Frontend uses plain JS for easier integration

Easily pluggable scoring strategies

JSONField used for dependencies for flexibility

⏳ Time Breakdown
Task	Time
Backend algorithm + API	~2 hrs
Frontend UI + integration	~1 hr
Testing + Validation	~30 mins
Documentation + Project setup	~30 mins
🚀 Future Improvements

Graph-based dependency resolver

Eisenhower Matrix visualization

User authentication

Suggestions powered by heuristics / ML

Drag-and-drop UI for tasks

🔗 Git Commit Instructions

Initialize commit history using the included script:

chmod +x create_commits.sh
./create_commits.sh


Then push to GitHub:

git branch -M main
git remote add origin https://github.com/<your-username>/Singularium_Internship_Assignment_2025.git
git push -u origin main

🎯 Final Notes

This repository is fully ready for submission and evaluation for the Singularium Software Development Internship 2025.
It demonstrates:

Algorithm design

Full-stack development

Clean architecture

Problem-solving and documentation




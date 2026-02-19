# Fullstack Docker Compose Project

A complete full‑stack application running with **React (frontend)**, **Node.js/Express (backend)**, and **PostgreSQL (database)** — fully containerized and orchestrated using **Docker Compose**.

This project demonstrates essential DevOps skills:
- Containerizing applications  
- Multi‑stage Docker builds  
- Running databases in containers  
- Service‑to‑service networking  
- Persistent volumes  
- Orchestrating multiple services with Docker Compose  

---

## 📁 Project Structure

fullstack-docker-compose/
│
├── backend/
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── Dockerfile
│   ├── package.json
│   └── src/
│
├── docker-compose.yml
└── README.md

Code

---

##  Architecture Overview

frontend (React + Nginx)
|
|  HTTP (port 5000)
v
backend (Node.js + Express)
|
|  PostgreSQL connection (port 5432)
v
database (PostgreSQL)

Code

All services run inside Docker and communicate through an internal Docker network.

---

##  Docker Compose Commands

### Start all services
```bash
docker compose up --build
Stop all services
bash
docker compose down
Application URLs
Code
+------------+------------------------+------------------------------+
| Service    | URL                    | Description                  |
+------------+------------------------+------------------------------+
| Frontend   | http://localhost:3000  | React app served by Nginx    |
| Backend    | http://localhost:5000  | Express API                  |
| PostgreSQL | localhost:5432         | Database (optional access)   |
+------------+------------------------+------------------------------+
Screenshots
Add your screenshots here:

react-running-locally.png

react-running-in-docker.png

compose-up.png

compose-frontend.png

compose-backend.png

Technologies Used
React (Frontend)

Node.js + Express (Backend)

PostgreSQL (Database)

Docker (Containerization)

Docker Compose (Orchestration)

Nginx (Frontend web server)

Docker Compose Services
Frontend
Built using multi‑stage Dockerfile

Served by Nginx

Exposed on port 3000

Backend
Node.js + Express

Exposed on port 5000

Connects to PostgreSQL using environment variables

Database
PostgreSQL 15

Persistent storage using Docker volume pgdata

How to Run the Project
Clone the repository

Navigate into the project folder

Run:

bash
docker compose up --build
Open browser:

Frontend → http://localhost:3000

Backend → http://localhost:5000

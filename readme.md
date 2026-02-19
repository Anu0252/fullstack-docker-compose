# Fullstack Docker Compose Project

A complete full stack application running with **React (frontend)**, **Node.js/Express (backend)**, and **PostgreSQL (database)** — fully containerized and orchestrated using **Docker Compose**.

This project demonstrates essential DevOps skills:

- Containerizing applications  
- Multi‑stage Docker builds  
- Running databases in containers  
- Service‑to‑service networking  
- Persistent volumes  
- Orchestrating multiple services with Docker Compose  

---
## Project Structure
```

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
```
---

##  Architecture Overview
```
                 +------------------+
                 |     Frontend     |
                 | React + Nginx    |
                 |  (Port 3000)     |
                 +---------+--------+
                           |
                           | HTTP (5000)
                           v
                 +------------------+
                 |     Backend      |
                 | Node.js + Express|
                 |   (Port 5000)    |
                 +---------+--------+
                           |
                           | PostgreSQL (5432)
                           v
                 +------------------+
                 |    Database      |
                 |   PostgreSQL     |
                 |   (Port 5432)    |
                 +------------------+
```
All services run inside Docker and communicate through an internal Docker network.

---

##  Docker Compose Setup

### Build and start all services

```bash
docker compose up --build
```

## Stop all services

```bash
docker compose down
```

##  Application URLs

```bash
+------------+------------------------+------------------------------+
| Service    | URL                    | Description                  |
+------------+------------------------+------------------------------+
| Frontend   | http://localhost:3000  | React app served by Nginx    |
| Backend    | http://localhost:5000  | Express API                  |
| PostgreSQL | localhost:5432         | Database (optional access)   |
+------------+------------------------+------------------------------+
```
## screenshots

### React running locally
<img width="600" height="700" alt="react-running-locally" src="https://github.com/user-attachments/assets/b7eca5b3-ce3b-42ed-87df-b3799e5d41eb" />

### React running in Docker
<img width="600" height="692" alt="react-running-in-docker" src="https://github.com/user-attachments/assets/301231f9-0c77-43bc-9f1c-3692032f41bd" />


### Docker Compose Up
<img width="603" height="77" alt="compose-up" src="https://github.com/user-attachments/assets/a0e249d6-e46b-4fad-8a86-00b127f5e1a6" />


### Frontend via Compose
<img width="600" height="720" alt="compose-frontend" src="https://github.com/user-attachments/assets/97316fde-7510-400f-83b1-8b4a6c5e29f6" />

### Backend via Compose
<img width="766" height="247" alt="compose-backend" src="https://github.com/user-attachments/assets/7a8801ac-c18f-4e97-9705-d050cad80fd1" />

## Technologies used

- React (Frontend)
- Node.js + Express (Backend)
- PostgreSQL (Database)
- Docker (Containerization)
- Docker Compose (Orchestration)
- Nginx (Frontend web server)
---

## Docker Compose Services

### Frontend
- Built using multi‑stage Dockerfile
- Served by Nginx
- Exposed on port 3000

### Backend
- Node.js + Express
- Exposed on port 5000
- Connects to PostgreSQL using environment variables

### Database
- PostgreSQL 15
- Persistent storage using Docker volume pgdata
---

## How to Run the Project

1.Clone the repository

2.Navigate into the project folder

3.Run:

```bash
docker compose up --build
```
4.Open browser:
- Frontend → http://localhost:3000
- Backend → http://localhost:5000

# PRV Nurse - Backend Service

![PRV Nurse](https://img.shields.io/badge/PRV%20Nurse-Healthcare%20Platform-blue)
![Node.js](https://img.shields.io/badge/Node.js-18.x-green)
![Express](https://img.shields.io/badge/Express-4.x-lightgrey)
![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-brightgreen)

PRV Nurse is a comprehensive platform designed to bridge the gap between patients and specialized nurses. This repository contains the backend API and machine learning services powering the PRV Nurse platform.

## Features

- **Role-Based Authentication**: Secure JWT-based authentication for Nurses, Patients, and Administrators.
- **Nurse Onboarding & Verification**: Robust endpoints to handle nurse profiles, licenses, and availability.
- **Patient Requests**: Endpoints for patients to find and request specialized care.
- **Booking Management**: Complete lifecycle management for appointments (Pending, Approved, Ongoing, Completed).
- **Admin Dashboard API**: Management endpoints for administrative oversight.
- **Machine Learning Integration**: Python-based recommendation engine for matching patients with the best-suited nurses.

## Architecture

The backend consists of two main components:
1. **Main API (Node.js/Express)**: Handles routing, authentication, business logic, and database interactions.
2. **Recommendation Service (Python)**: A specialized service that processes nurse and patient data to suggest optimal matches.

## Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- MongoDB (local or Atlas)
- Python 3.9+ (for the ML service)

## Setup and Installation

### 1. Main Backend (Node.js)

Navigate to the backend directory and install dependencies:

```bash
cd backend
npm install
```

Set up your environment variables. Create a `.env` file in the `backend` directory (a template is provided below):

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/prvnurse
JWT_SECRET=your_jwt_secret_key
```

Start the development server:

```bash
npm run dev
```

### 2. Machine Learning Service (Python)

Navigate to the `ml-service` directory:

```bash
cd ml-service
```

Create a virtual environment and install dependencies (e.g., using `uv` or `pip`):

```bash
python -m venv venv
# Activate the venv (Windows: venv\Scripts\activate, Mac/Linux: source venv/bin/activate)
pip install -r requirements.txt
```

Run the service:

```bash
uvicorn main:app --reload --port 8000
```

## API Documentation

- **Authentication**: `POST /api/auth/register`, `POST /api/auth/login`, `GET /api/auth/me`
- **Nurses**: `GET /api/nurses`, `GET /api/nurses/:id`
- **Patients**: `GET /api/patients`
- **Bookings**: `POST /api/bookings`, `GET /api/bookings/:id`, `PUT /api/bookings/:id/status`
- **Admin**: `GET /api/admin/stats`

## License

This project is licensed under the MIT License - see the LICENSE file for details.

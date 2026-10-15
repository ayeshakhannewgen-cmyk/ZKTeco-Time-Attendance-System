# ZKTeco Time Attendance System

A time attendance management system using ZKTeco Push SDK with PostgreSQL backend and Python Flask server.

## Features

- Receive real-time attendance data from ZKTeco devices via HTTP push
- Store attendance records in PostgreSQL database
- Employee management
- Device registration and tracking
- RESTful API endpoints
- Docker ready

## Prerequisites

- Python 3.8+
- PostgreSQL database
- ZKTeco devices with Push SDK capability

## Installation

1. Clone the repository
2. Create a virtual environment:
   `ash
   python -m venv venv
   `
3. Activate the virtual environment:
   `ash
   # On Windows
   venv\Scripts\activate
   # On Unix or MacOS
   source venv/bin/activate
   `
4. Install dependencies:
   `ash
   pip install -r requirements.txt
   `
5. Configure environment variables in .env file:
   `ash
   cp .env.example .env
   # Edit .env with your database credentials
   `
6. Initialize the database:
   `ash
   python src/database.py
   `

## Usage

1. Start the Flask server:
   `ash
   python src/app.py
   `
2. Configure your ZKTeco devices to push data to:
   `
   http://your-server-ip:5000/push
   `
3. For device registration, devices can POST to:
   `
   http://your-server-ip:5000/devices
   `

## API Endpoints

- POST /push - Receive attendance data from ZKTeco devices
- POST /devices - Register/update device information
- GET /health - Health check endpoint

## Database Schema

The system creates three tables:
- mployees - Employee information
- ttendance_logs - Attendance punch records
- devices - Registered ZKTeco devices

## Configuration

Edit the .env file to configure:
- Database connection parameters
- Server host and port
- Debug mode

## License

MIT

# Pittsburgh2Peers Backend Service

Welcome to Pittsburgh2Peers, a web app designed to make student life in Pittsburgh easier, safer, and more connected. Built in a week, this app focuses on helping college communities come together, share resources, and form meaningful connections. Whether you are looking to split an Uber from the airport, share a U-Haul, or meet fellow students, Pittsburgh2Peers is here to help.

Flask API and admin dashboard for the Pittsburgh2Peers web app. This service handles user registration, token management, carpool and U-Haul requests, and a lightweight admin view.

- Demo: https://pittsburgh2peers.vercel.app/
- Pre-recorded demo: https://drive.google.com/file/d/1s66ymQwJZS2dXAcxsINda0tIlEeZwTeS/view?usp=drive_link
- Frontend repo: https://github.com/abhishek-sankar/Pittsburgh2Peers

## Overview

Pittsburgh2Peers was initially launched to assist students arriving in Pittsburgh. It quickly grew into a tool for:

- Airport ride sharing to split costs and travel safely
- U-Haul sharing for coordinated bulk moves
- Making connections when arriving in a new city

With over 1,000 unique visits, 350 Andrew sign-ins, and 150 completed requests in 2 weeks, Pittsburgh2Peers seems to be an app worth pursuing.

## Tech Stack

- Backend: Python 3, Flask
- Database: SQLite
- Frontend: React.js
- Hosting: Vercel
- Analytics: Mixpanel

## Local Setup

1. Create and activate a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the server:

```bash
python flask_app.py
```

The app runs on http://127.0.0.1:5000 with debug mode enabled.

## Database

SQLite database file is stored at `routes/db/database.db`. The API uses this file directly through `routes/db/dbInteraction.py`.

## Routes

All routes accept JSON request bodies and return JSON responses unless noted.

### User

- POST, PUT `/registrationSuccess`
- POST `/generateToken`
- POST `/userProfileComplete`
- POST, PUT `/updateUserProfile`
- POST `/getUserProfileDetails`
- POST `/getFlags`

### Carpool

- POST, PUT `/carPoolRequest`
- POST `/getAllCarPoolRequests`
- POST `/offerCarPool`
- POST `/getMyCarPoolOffers`

### U-Haul

- POST, PUT `/uHaulRequest`
- POST `/getAllUHaulRequests`
- POST `/getMyUHaulOffers`

### Admin

- GET `/adminDashboard` (renders HTML at `templates/adminDashboard.html`)

## Features

1. Seamless user flow with a simple request and offer process.
2. Real-time matching with time and date filters.
3. Community feedback integration to improve the experience quickly.
4. Data-driven insights via analytics.

## Development Story

We built Pittsburgh2Peers after noticing gaps in how students connect and coordinate when they first arrive. The team collaborated intensively for a week to develop the app.

Key moments:

- Resolved early bugs affecting date matching within hours of feedback.
- Extended functionality to include U-Haul sharing after identifying a common student need.
- Prioritized accessibility and user-centric design for a better experience.

## Next Steps

Although the app was tailored for move-in season, we are exploring how to expand its utility throughout the year. Potential ideas include:

- Event coordination for study groups or campus events.
- Local community engagement to connect students with city resources.

## Acknowledgments

Thanks to the CMU and UPitt communities for their feedback, and to the Swartz Center for Entrepreneurship for guidance. We appreciate every user who trusted us to make their journey smoother.

## Notes

- CORS is enabled for all routes.
- Tokens are stored in the database and validated server-side.

## Contributions

Contributions are welcome. Please open a pull request with a clear description of changes.

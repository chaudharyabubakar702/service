# Vehicle Emergency Assistance Demo

A simple Pakistan-based vehicle emergency assistance app built with:

- **Backend:** Django + Django REST Framework
- **Database:** SQLite for local development
- **Frontend:** React + Vite
- **Real-time-ready architecture:** the scaffold is API-first and easy to extend with WebSockets later

## What is included

- Mechanic listings with location and availability
- Emergency service request creation
- Nearby mechanic lookup using latitude/longitude
- Demo data seed command
- React dashboard that shows live requests and nearby mechanics

## Folder structure

```text
service/
├── backend/
│   ├── config/
│   └── dispatch/
├── frontend/
│   └── src/
└── README.md
```

## Local setup

### 1) Backend

```bash
cd /home/workspace/service/backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
python manage.py makemigrations
python manage.py migrate
python manage.py seed_demo
python manage.py runserver
```

### 2) Frontend

```bash
cd /home/workspace/service/frontend
npm install
cp .env.example .env
npm run dev
```

## Demo data

The backend seed command creates sample Pakistan-based records such as:

- Lahore mechanic: `Ali Auto Rescue`
- Karachi mechanic: `Karachi Bike Help`
- Islamabad mechanic: `Islamabad Roadside Pro`
- Demo requests for tire burst and engine problem cases

## API endpoints

- `GET /api/mechanics/nearby/?lat=...&lng=...&radius=...`
- `GET /api/requests/`
- `POST /api/requests/`
- `GET /api/offers/`
- `GET /api/messages/`

## Notes

- SQLite is fine for development.
- For production use PostgreSQL.
- This scaffold is intentionally lightweight and easy to extend.
- If you want, the next step can be adding login, WebSockets chat, and offer negotiation.


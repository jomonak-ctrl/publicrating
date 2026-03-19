# PublicRating

This is a full-stack web application using Angular (frontend), Node.js/Express (backend), and MySQL (database).

## Getting Started

### Prerequisites
- Node.js and npm installed
- MySQL installed and running

### Setup

#### Install dependencies
```
cd backend
npm install
cd ../PublicRating/frontend
npm install
```

#### Start full stack (recommended)
- In VS Code, run task `dev:fullstack`
- This task automatically:
	- frees stale listeners on ports `3000` and `4200`
	- starts backend first and waits until `http://127.0.0.1:3000/test-mysql` responds
	- starts frontend on `http://localhost:4200`

#### Manual startup (if needed)
```
cd backend
npm start
```
```
cd PublicRating/frontend
npm start
```

### Backend upload/download smoke test
Run this to validate bribery attachment upload + download flow end-to-end (including max-attachment limit checks):
```
cd backend
npm run smoke:attachments
```
Optional: override API base URL if backend is not running on `http://127.0.0.1:3000`:
```
$env:API_BASE_URL="http://127.0.0.1:3000"
npm run smoke:attachments
```

## Project Structure
- `PublicRating/frontend/` - Angular app
- `backend/` - Node.js/Express API with MySQL

## Environment Variables
- MYSQL_HOST
- MYSQL_USER
- MYSQL_PASSWORD
- MYSQL_DATABASE
- PORT
- SMTP_HOST
- SMTP_PORT
- SMTP_SECURE
- SMTP_USER
- SMTP_PASS
- SMTP_FROM

Use `backend/.env.example` as reference.

Notes:
- Database variables can still fall back to defaults in `backend/db.js`.
- SMTP variables are required for OTP email delivery (profile update OTP and forgot-password OTP).
- This backend reads environment variables from the process environment; if you use a `.env` file, load it via your runtime/tooling.

---

For further customization, add your own API routes and Angular components as needed.

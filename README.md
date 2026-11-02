# SurpriseLover — Full-stack romantic surprise website

A responsive React + Node.js/Express + MySQL starter project. It includes a public romantic landing page, photo-memory gallery, relationship timeline, animated love letter, secret-message reveal, countdown, music toggle (uses your own audio file), admin login/dashboard, editable content, photo upload, and optional Telegram bot notification integration.

## Requirements
- Node.js 18+
- MySQL 8+

## 1) Database setup
Create a MySQL database and user, then import `backend/database.sql` in MySQL Workbench/phpMyAdmin:

```sql
CREATE DATABASE surprise_lover CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Then import `backend/database.sql`.

## 2) Backend
```bash
cd backend
copy .env.example .env
npm install
npm run dev
```
Edit `.env` with your MySQL details and a long random `JWT_SECRET`.

Default API: http://localhost:5000

## 3) Frontend
Open a second terminal:
```bash
cd frontend
npm install
npm run dev
```
Open the Vite URL shown (usually http://localhost:5173).

## 4) Create your admin account
After backend starts, run:
```bash
cd backend
npm run create-admin -- --email you@example.com --password 'ChooseAStrongPassword123!'
```
Then use the Admin button in the website to log in. Do not use a real password you use elsewhere.

## 5) Personalize it
- Log in and use the dashboard to change names, headline, letter, special date, and timeline entries.
- Upload your own photos to the gallery. The included sample cards are decorative placeholders.
- Add your own audio file at `frontend/public/our-song.mp3` if you have permission to use it; the music button will play it.
- Change the text in the “secret message” section to something meaningful and respectful.

## 6) Telegram (optional)
Create a bot with Telegram's official BotFather, add `TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID` in `.env`, then set `VITE_API_URL` for production. The admin dashboard has a test-notification endpoint. A bot cannot silently message a person who has never opened/started the bot; the recipient must start it first. Never put the bot token in frontend code.

## 7) Deploy
- Frontend: Vercel or Netlify (build command `npm run build`, output `dist`). Set `VITE_API_URL` to your deployed backend URL.
- Backend: Render, Railway, or another Node host. Set all `.env` values in host environment settings, and use a managed MySQL service.
- Do not deploy with the example JWT secret or database credentials.

## Security notes
Passwords are hashed with bcrypt; protected admin routes use JWT; upload file types and size are restricted; server-side validation is included. Use HTTPS in production, keep dependencies updated, and do not upload private/intimate photos without clear consent.

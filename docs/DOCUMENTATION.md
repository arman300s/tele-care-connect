# TeleCare Connect — Documentation

## Table of Contents

1. [Project Overview](#project-overview)
2. [Architecture Overview](#architecture-overview)
3. [User Guide — Patients](#user-guide--patients)
4. [User Guide — Healthcare Providers](#user-guide--healthcare-providers)
5. [Deployment Guide](#deployment-guide)
6. [Configuration Reference](#configuration-reference)
7. [API Reference](#api-reference)
8. [Security & Privacy](#security--privacy)
9. [Contributing](#contributing)
10. [License](#license)

---

## Project Overview

TeleCare Connect is an open-source telemedicine platform that enables patients in underserved and geographically remote communities to access qualified healthcare providers through video, audio, and text-based consultations.

**Goal:** Advance UN SDG 3 (Good Health and Well-Being) by removing barriers to primary healthcare including distance, transportation costs, and clinic wait times.

**Target users:**
- Patients in low- and middle-income countries (LMICs) with limited access to in-person care
- Healthcare providers and clinics seeking to extend their reach
- Health ministries, NGOs, and community health organisations deploying their own instances

---

## Architecture Overview

TeleCare Connect is built as a web-based application with the following high-level components:

```
┌──────────────────────────────────────────────────────────┐
│                      Client (Browser)                    │
│     Patient UI  │  Provider UI  │  Admin Dashboard       │
└──────────────────────────┬───────────────────────────────┘
                           │ HTTPS
┌──────────────────────────▼───────────────────────────────┐
│                    Application Server                    │
│   REST API  │  WebRTC Signalling  │  Authentication      │
└──────────────────────────┬───────────────────────────────┘
                           │
┌──────────────────────────▼───────────────────────────────┐
│                       Database                           │
│           User records │ Appointments │ Logs             │
└──────────────────────────────────────────────────────────┘
```

**Key technologies:**
- **Frontend:** Modern JavaScript (HTML/CSS/JS or framework of choice)
- **Backend:** Node.js REST API
- **Real-time communication:** WebRTC for video/audio, WebSocket for chat
- **Database:** Configurable (PostgreSQL recommended for production)

---

## User Guide — Patients

### Registering an Account

1. Navigate to the TeleCare Connect homepage.
2. Click **Sign Up** and complete the registration form with your name, email address, and a secure password.
3. Verify your email address via the confirmation link sent to your inbox.
4. Log in with your credentials.

### Booking a Consultation

1. From your dashboard, click **Book a Consultation**.
2. Select the type of consultation: **Video**, **Audio**, or **Text/Chat**.
3. Choose an available healthcare provider and a time slot that suits you.
4. Confirm your booking. You will receive a confirmation notification.

### Joining a Consultation

1. At the scheduled time, log in and navigate to **My Appointments**.
2. Click **Join** next to your upcoming appointment.
3. Allow your browser to access your camera and microphone when prompted (for video/audio consultations).
4. Your provider will join the session from their end.

### After the Consultation

- A summary or notes from the consultation may be available in **My Records** (subject to provider input).
- You can rate your experience and leave feedback.

---

## User Guide — Healthcare Providers

### Setting Up Your Provider Profile

1. Register using your professional credentials. An admin may need to verify your account.
2. Complete your profile: specialty, languages spoken, availability schedule.

### Managing Appointments

1. View all upcoming consultations in your **Provider Dashboard**.
2. Accept or decline appointment requests.
3. Add consultation notes to a patient's record after each session.

### Conducting Consultations

1. At the scheduled time, navigate to **My Appointments** and click **Join**.
2. The WebRTC-based interface will connect you to the patient.
3. Use the in-session chat for sharing notes or links during the consultation.

---

## Deployment Guide

### Requirements

- Node.js v18+
- PostgreSQL 14+ (or compatible database)
- A server with HTTPS (required for WebRTC camera/microphone access)
- STUN/TURN server for WebRTC in production (e.g., coturn)

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/arman300s/tele-care-connect.git
cd tele-care-connect

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env
# Edit .env — see Configuration Reference below

# 4. Run database migrations
npm run migrate

# 5. Build the application
npm run build

# 6. Start the server
npm start
```

For containerised deployments, a `Dockerfile` and `docker-compose.yml` are provided in the repository root (if applicable).

---

## Configuration Reference

| Variable             | Description                                          | Default        |
|----------------------|------------------------------------------------------|----------------|
| `PORT`               | Port the application listens on                      | `3000`         |
| `DATABASE_URL`       | PostgreSQL connection string                         | —              |
| `JWT_SECRET`         | Secret key for signing authentication tokens         | —              |
| `TURN_SERVER_URL`    | TURN server URL for WebRTC NAT traversal             | —              |
| `TURN_SERVER_USER`   | TURN server username                                 | —              |
| `TURN_SERVER_PASS`   | TURN server credential                               | —              |
| `NODE_ENV`           | `development` or `production`                        | `development`  |

> **Security note:** Never commit your `.env` file or any secrets to version control.

---

## API Reference

All API endpoints are prefixed with `/api/v1`.

| Method | Endpoint                      | Description                        | Auth required |
|--------|-------------------------------|------------------------------------|---------------|
| POST   | `/auth/register`              | Register a new user                | No            |
| POST   | `/auth/login`                 | Authenticate and receive a token   | No            |
| GET    | `/appointments`               | List appointments for current user | Yes           |
| POST   | `/appointments`               | Create a new appointment           | Yes           |
| GET    | `/appointments/:id`           | Get appointment details            | Yes           |
| DELETE | `/appointments/:id`           | Cancel an appointment              | Yes           |
| GET    | `/providers`                  | List available providers           | Yes           |
| GET    | `/providers/:id`              | Get provider profile               | Yes           |

Authentication uses **Bearer tokens (JWT)**. Include the token in the `Authorization` header:

```
Authorization: Bearer <token>
```

---

## Security & Privacy

TeleCare Connect is designed with patient privacy as a core principle, in alignment with responsible data handling practices:

- **Encryption in transit:** All communication between client and server uses HTTPS/TLS. WebRTC media streams are encrypted end-to-end using DTLS-SRTP.
- **Authentication:** Users authenticate via secure, hashed credentials. Sessions are managed with short-lived JWTs.
- **Data minimisation:** Only data necessary for the provision of care is collected.
- **Access control:** Role-based access ensures patients can only access their own records, and providers can only access records of their own patients.
- **No third-party tracking:** The platform does not embed third-party advertising or analytics trackers.
- **Responsible disclosure:** If you discover a security vulnerability, please report it responsibly by opening a GitHub Issue marked **[Security]** or contacting the maintainers directly, rather than disclosing it publicly.

> **Note for deployers:** Organisations deploying TeleCare Connect for real patient care must ensure compliance with applicable local health data regulations (e.g., GDPR, HIPAA, or equivalent national standards).

---

## Contributing

Contributions are welcome! Please read our [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines on how to report bugs, suggest features, and submit pull requests.

---

## License

TeleCare Connect is released under the [MIT License](../LICENSE). You are free to use, modify, and distribute the software, including for deployment in healthcare settings, provided the license notice is retained.

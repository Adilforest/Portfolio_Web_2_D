# Portfolio Platform

A full-stack portfolio management web app built with Node.js, Express, EJS, and MongoDB — featuring user authentication, role-based access control, and third-party API integrations.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-B4CA65?style=flat)

## Overview

A server-rendered portfolio platform where administrators manage image-based portfolio items (carousels of up to three photos per entry, with title and description). Editors can add items but cannot delete or modify them. Authentication uses bcrypt-hashed passwords and express-session; email notifications are sent via Nodemailer on registration.

## Features

- User registration and login with bcrypt password hashing
- Session-based authentication (`express-session`)
- Two roles: **admin** (full CRUD) and **editor** (create only)
- Portfolio items with multi-image carousel, title, description, and timestamps
- Image upload via Multer
- Welcome email on registration (Nodemailer)
- Yahoo Finance data route (`/yahoo`)
- 404 custom error page
- EJS server-side templating

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Runtime | Node.js |
| Framework | Express 4 |
| Templating | EJS |
| Database | MongoDB (Mongoose ODM) |
| Auth | bcrypt + express-session |
| File upload | Multer |
| Email | Nodemailer |
| Config | dotenv |

## Getting Started

### Prerequisites

- Node.js 16+
- A running MongoDB instance (local or Atlas)

### Installation

```bash
git clone https://github.com/Adilforest/Portfolio_Web_2_D.git
cd Portfolio_Web_2_D
npm install
```

Create a `.env` file in the project root:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/portfolio_project
SESSION_SECRET=your_session_secret
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password
```

Start the development server:

```bash
npx nodemon app.js
# or
node app.js
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Routes

| Method | Path | Description |
|--------|------|-------------|
| GET | `/` | Home — gallery of portfolio items |
| POST | `/auth/register` | Register a new user |
| POST | `/auth/login` | Log in |
| GET | `/auth/logout` | Log out |
| GET | `/admin/images` | List portfolio items (admin/editor) |
| POST | `/admin/images` | Add a portfolio item |
| POST | `/admin/images/delete/:id` | Delete a portfolio item (admin only) |
| GET | `/yahoo` | Yahoo Finance data view |

---

Adil Ormanov — [GitHub](https://github.com/Adilforest)

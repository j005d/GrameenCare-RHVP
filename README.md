# 🌿 Rural Health Volunteer Platform (RHVP)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D%2016.0.0-brightgreen)](https://nodejs.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

> Connecting healthcare volunteers with rural communities to bridge the healthcare gap in underserved areas.

## 📋 Table of Contents

- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [Roadmap](#roadmap)
- [License](#license)

## 🌐 Overview

Rural Health Volunteer Platform is a comprehensive web-based application designed to connect health volunteers, doctors, NGOs, and rural citizens. The platform enables real-time support, health awareness campaigns, and local medical aid coordination to strengthen healthcare delivery in rural areas.

## 💡 Problem Statement

Rural areas face critical healthcare challenges:

- **Healthcare Professional Shortage**: Limited access to doctors and medical staff
- **Delayed Medical Support**: Emergency services often arrive too late
- **Low Health Awareness**: Lack of education on preventive health practices
- **Disconnected Volunteers**: NGOs and volunteers lack structured platforms to coordinate efforts

## ✨ Features

### 👩‍⚕️ Volunteer & Doctor Dashboard
- **Profile Management**: Create detailed profiles with skills (first aid, nursing, awareness training)
- **Task Management**: View and accept assignments in real-time
- **Gamification**: Earn badges, certificates, and performance points
- **Availability Calendar**: Set and manage availability schedules

### 🏥 Rural User Portal
- **Medical Help Requests**: Submit emergency or routine medical assistance requests
- **Health Camp Registration**: Book slots for free health camps and screenings
- **Multilingual Support**: Access content in local languages (Hindi, Telugu, Tamil, Bengali, etc.)
- **Health Resource Library**: Browse preventive health tips and educational content

### 📞 Telehealth Services
- **Video Consultations**: Connect with certified doctors via WebRTC
- **Chat Support**: Real-time text communication with volunteers
- **AI Symptom Checker**: Primary guidance bot for common health concerns
- **Prescription Management**: Digital prescription storage and tracking

### 📊 NGO / Admin Control Panel
- **Team Management**: Organize and deploy volunteer teams efficiently
- **Campaign Creation**: Plan and execute health drives (vaccination, blood donation, etc.)
- **Analytics Dashboard**: Track impact metrics, volunteer performance, and community health trends
- **Resource Allocation**: Manage medical supplies and equipment distribution

### 🌍 Community Health Awareness
- **Educational Content**: Health blogs, video tutorials, and infographics
- **Interactive Quizzes**: Gamified learning on sanitation, hygiene, and disease prevention
- **Push Notifications**: Timely alerts on health advisories and upcoming camps
- **Community Forums**: Peer-to-peer health discussion boards

## 💻 Tech Stack

### Frontend
- **Framework**: React.js 18+ / Next.js 14+
- **UI Library**: Tailwind CSS, Shadcn/ui
- **State Management**: React Context API / Redux Toolkit
- **Icons**: Lucide React

### Backend
- **Runtime**: Node.js 16+
- **Framework**: Express.js
- **Real-time**: Socket.io

### Database
- **Primary**: MongoDB (User data, campaigns, requests)
- **Cache**: Redis (Session management)
- **Storage**: AWS S3 / Firebase Storage (Media files)

### Authentication & Security
- **Auth**: Firebase Authentication / JWT
- **OAuth**: Google, Facebook login integration
- **Encryption**: bcrypt for password hashing

### Communication
- **Video/Voice**: WebRTC, Twilio API
- **Chat**: Socket.io
- **SMS**: Twilio SMS API

### AI & ML (Optional)
- **Chatbot**: OpenAI API / Google Dialogflow
- **Symptom Analysis**: Custom ML model with TensorFlow.js

### Deployment
- **Hosting**: AWS EC2 / Vercel / Render
- **CDN**: Cloudflare
- **CI/CD**: GitHub Actions
- **Monitoring**: Sentry, Google Analytics

## 🚀 Installation

### Prerequisites
```bash
node >= 16.0.0
npm >= 8.0.0
MongoDB >= 5.0
```

### Clone Repository
```bash
git clone https://github.com/yourusername/rural-health-volunteer-platform.git
cd rural-health-volunteer-platform
```

### Environment Setup

Create a `.env` file in the root directory:

```env
# Server Configuration
NODE_ENV=development
PORT=5000
MONGODB_URI=mongodb://localhost:27017/rhvp

# Firebase Configuration
FIREBASE_API_KEY=your_api_key
FIREBASE_AUTH_DOMAIN=your_auth_domain
FIREBASE_PROJECT_ID=your_project_id

# Twilio Configuration
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_API_KEY=your_api_key
TWILIO_API_SECRET=your_api_secret

# OpenAI Configuration (Optional)
OPENAI_API_KEY=your_openai_key

# AWS S3 Configuration
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
AWS_BUCKET_NAME=your_bucket_name
AWS_REGION=your_region

# JWT Secret
JWT_SECRET=your_jwt_secret_key
```

### Install Dependencies

**Backend:**
```bash
cd backend
npm install
```

**Frontend:**
```bash
cd frontend
npm install
```

### Run Development Server

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend:**
```bash
cd frontend
npm run dev
```

Access the application at `http://localhost:3000`

## 📖 Usage

### For Volunteers/Doctors
1. Register with credentials and verification documents
2. Complete profile with skills and specializations
3. Browse available assignments in your area
4. Accept tasks and coordinate with rural communities
5. Conduct teleconsultations or on-ground visits

### For Rural Users
1. Register with basic information (mobile-first approach)
2. Request medical help or browse upcoming health camps
3. Book teleconsultation slots
4. Access health education content in local language
5. Participate in community health forums

### For NGO Admins
1. Create organization profile
2. Onboard and manage volunteer teams
3. Plan and execute health campaigns
4. Monitor impact through analytics dashboard
5. Generate reports for stakeholders

## 📁 Project Structure

```
rural-health-volunteer-platform/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── volunteer/
│   │   │   ├── rural-user/
│   │   │   ├── ngo/
│   │   │   └── common/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── utils/
│   │   ├── hooks/
│   │   └── App.js
│   └── package.json
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   ├── services/
│   │   └── server.js
│   └── package.json
├── docs/
├── .env.example
├── .gitignore
├── README.md
└── LICENSE
```

## 📡 API Documentation

### Authentication Endpoints

```
POST /api/auth/register - Register new user
POST /api/auth/login - User login
POST /api/auth/logout - User logout
GET /api/auth/verify - Verify JWT token
```

### Volunteer Endpoints

```
GET /api/volunteers - Get all volunteers
GET /api/volunteers/:id - Get volunteer by ID
PUT /api/volunteers/:id - Update volunteer profile
GET /api/volunteers/:id/tasks - Get assigned tasks
POST /api/volunteers/:id/accept-task - Accept assignment
```

### Rural User Endpoints

```
POST /api/requests - Create medical help request
GET /api/requests/:userId - Get user's requests
GET /api/camps - Get upcoming health camps
POST /api/camps/:id/register - Register for camp
```

### NGO Endpoints

```
POST /api/campaigns - Create new campaign
GET /api/campaigns - Get all campaigns
PUT /api/campaigns/:id - Update campaign
DELETE /api/campaigns/:id - Delete campaign
GET /api/analytics - Get platform analytics
```

### Telehealth Endpoints

```
POST /api/consultations/create - Create consultation room
GET /api/consultations/:id - Get consultation details
POST /api/consultations/:id/end - End consultation
POST /api/chat/send - Send chat message
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Standards
- Follow ESLint configuration
- Write meaningful commit messages
- Add unit tests for new features
- Update documentation as needed

## 🗺️ Roadmap

### Phase 1 (MVP) ✅
- [x] User authentication system
- [x] Basic volunteer and rural user portals
- [x] Medical help request system
- [x] Admin dashboard

### Phase 2 (Current)
- [ ] Telehealth video consultation
- [ ] AI symptom checker bot
- [ ] Multilingual support (5+ languages)
- [ ] Mobile app (React Native)

### Phase 3 (Future)
- [ ] Integration with Ayushman Bharat, PMJAY schemes
- [ ] Offline mode with data sync
- [ ] Advanced analytics with ML predictions
- [ ] Pharmacy integration for medicine delivery
- [ ] Ambulance tracking and dispatch system

## 🩺 Impact Metrics

- **500+** Registered volunteers
- **50+** Partner NGOs
- **10,000+** Rural users served
- **2,000+** Teleconsultations conducted
- **150+** Health camps organized

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Ministry of Health and Family Welfare, India
- National Health Mission
- All volunteer healthcare professionals
- Partner NGOs and community health workers

## 📞 Contact

**Project Maintainer**: Your Name  
**Email**: contact@rhvp.org  
**Website**: https://rhvp.org

---

**Made with ❤️ for rural India's health**

*If you find this project helpful, please consider giving it a ⭐ on GitHub!*

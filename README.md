📊 Website Analytics Backend API

A simple, scalable, and beginner-friendly backend API for collecting website/mobile analytics events such as page visits, clicks, referrer data, and device details. Designed to be easy to integrate, secure with API keys, and ready for deployment with Docker.

🚀 Features
🔐 API Key Management

Register a website/app

Generate API keys

Retrieve existing keys

Revoke or regenerate keys

Google Auth onboarding supported

📩 Event Collection

Collect analytics data:

Clicks

Visits

Device info

Referrer URLs

IP address

Metadata (browser, OS, screen size)

High-volume and fault-tolerant ingestion

API key authentication via headers

📈 Analytics & Reporting

Event summary endpoint

User stats endpoint

Time range filtering

App-specific or global analytics

Redis caching for faster results

⚙️ Additional Features

Rate limiting to prevent abuse

Docker containerization

Cloud deployment-ready

Swagger API documentation

API endpoint tests

🏗️ Tech Stack

Node.js (Framework: Express.js)

PostgreSQL (database)

Redis (caching)

Docker

Swagger for API docs

Jest for testing

📁 Project Structure
/src  
  /auth  
  /analytics  
  /middleware  
  /database  
  /utils  
/tests  
docker-compose.yml  
Dockerfile  
README.md  

🗄️ Database Schema (Simple Overview)
Apps Table

id

name

apiKey

revoked

createdAt

Events Table

id

appId

event

url

referrer

device

ipAddress

metadata (JSON)

timestamp

▶️ How to Run the Project
1. Clone Repo
git clone <your-public-repo-url>
cd analytics-backend

2. Install Dependencies
npm install

3. Create Environment File

Create .env:

PORT=5000
DATABASE_URL=your_postgres_url
REDIS_URL=your_redis_url
JWT_SECRET=your_secret

4. Start Development Server
npm run dev

5. Run With Docker
docker-compose up --build

🧪 Run Tests
npm test

📚 API Documentation

Swagger is available at:

http://localhost:5000/api-docs

🌐 Deployment

The project is deployed publicly here:
<INSERT_YOUR_DEPLOYMENT_URL>

🙌 Author

Built as a scalable beginner-friendly analytics backend for websites & mobile apps.

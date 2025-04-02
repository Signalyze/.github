# Signalyze

**Signalyze** is a traffic sign recognition system designed specifically for Indian roads. It uses computer vision and deep learning to detect and classify traffic signals into 37 predefined classes in real time. Once a traffic sign is recognized, the system provides an audio response, assisting drivers in navigating the busy roadways of India.

In addition to its core detection functionality, Signalyze includes an optional authentication system using NextAuth.js (Auth.js), Prisma ORM, and PostgreSQL. This authentication layer enables users to store each of their detections. The detections are then presented on a dashboard, where users can view overall statistics, detailed breakdowns (such as total detections, unique signs, and the most frequently detected sign), and interactive charts showing monthly trends by traffic sign type.

The system has been trained on the labelled **Indian Road Traffic Sign Detection dataset** and uses a YOLO v8 (small) model, achieving a mAP (mean Average Precision) of 82% (ranging from 50% to 95% across various classes).

## Table of Contents

- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Frontend Setup](#frontend-setup)
  - [Backend Setup](#backend-setup)
- [Environment Setup](#environment-setup)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Tech Stack

- **Frontend**:
  - [Next.js](https://nextjs.org/)
  - [shadcn UI](https://ui.shadcn.com/)
  - [TailwindCSS](https://tailwindcss.com/)
  - [NextAuth.js (Auth.js)](https://authjs.dev)
  - Hosted on [Vercel](https://vercel.com/)

- **Backend**:
  - [FastAPI](https://fastapi.tiangolo.com/)

- **Model**:
  - [YOLO v8s](https://github.com/ultralytics/ultralytics)
  - [Indian Road Traffic Sign Detection dataset](https://ieee-dataport.org/documents/irtsd-datasetv1-indian-road-traffic-sign-detection-dataset)
  - [Annotated Indian Road Traffic Sign Detection dataset on Roboflow](https://universe.roboflow.com/aaa-t4bs0/my-second-project-eby1m/dataset/4)

## Getting Started

### Prerequisites

- **[Node.js](https://nodejs.org)** (v18 or above)
- **[Python](https://www.python.org)** (v3.8 or above)
- **[Git](https://git-scm.com/)**
- **[PostgreSQL](https://www.postgresql.org)**

### Frontend Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Signalyze/www.git
   cd www
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Prisma Setup:**
   
   - Ensure you have your database credentials set in your environment variables (see [Environment Setup](#environment-setup) below).
   - Run Prisma migrations to set up your database schema:
     ```bash
     npx prisma migrate dev --name init
     ```
   - (Optional) Open Prisma Studio to inspect your data:
     ```bash
     npx prisma studio
     ```

4. **NextAuth Setup:**   
   - Make sure you have the required environment variables set (see [Environment Setup](#environment-setup) below).

5. **Run the development server:**
     ```bash
     npm run dev
     ```
     Open [localhost:3000](http://localhost:3000) in your browser.

### Backend Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Signalyze/backend.git
   cd backend
   ```

2. **Create a virtual environment and activate it**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies and run the FastAPI server**:
   ```bash
   pip install -r requirements.txt
   uvicorn index:app --reload
   ```
   The API will be available at [localhost:8000](http://localhost:8000). Make sure this URL matches the `NEXT_PUBLIC_API_URL` in your environment settings.

## Environment Setup

Create a `.env` file in the root of the frontend project as shown below:

```env
# Detection API URL
NEXT_PUBLIC_API_URL=http://localhost:8000

# Connect to Database via connection pooling
DATABASE_URL=postgresql://username:password@localhost:5432/signalyze_db?pgbouncer=true
# Direct connection to the database. Used for migrations.
DIRECT_URL=postgresql://username:password@localhost:5432/signalyze_db

# NextAuth configuration
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your-generated-secret

# Resend confirmation
RESEND_API_KEY=your-resend-api-key
EMAIL_FROM=your-email@example.com

```

### Steps to Generate / Find Keys:

- **NEXTAUTH_SECRET**:  
  Generate a secret using:
  ```bash
  openssl rand -base64 32
  # or
  npx auth secret
  ```
  

- **DATABASE_URL & DIRECT_URL**:  
  - For local PostgreSQL, use the connection string format:  
    `postgresql://username:password@localhost:5432/your_database`  
  - For Supabase, check your project’s settings on the Supabase dashboard, click on connect button and copy the connection string.

- **RESEND_API_KEY & EMAIL_FROM**:  
  - Sign up at [Resend](https://resend.com/) and get an API key with sending access.  
  - Verify your email domain on Resend and use that address for `EMAIL_FROM`.

## Contributing

We welcome contributions from the community! If you would like to contribute to Signalyze, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes with clear and descriptive messages.
4. Submit a pull request detailing your changes.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions, feedback, or support, please create an issue on the respective repository.

# Signalyze

**Signalyze** is a traffic sign recognition system designed specifically for Indian roads. It uses computer vision and deep learning to detect and classify traffic signals into 37 predefined classes in real time. Once a traffic sign is recognized, the system provides an audio response, assisting drivers in navigating the busy roadways of India.

The system has been trained on labelled **Indian Road Traffic Sign Detection dataset** and uses a YOLO v8 (small) model, achieving a mAP (mean Average Precision) of 82% (ranging from 50% to 95% across various classes).

## Table of Contents

- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Frontend Setup](#frontend-setup)
  - [Backend Setup](#backend-setup)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Tech Stack

- **Frontend**:
  - [Next.js](https://nextjs.org/)
  - [shadcn UI](https://ui.shadcn.com/)
  - [TailwindCSS](https://tailwindcss.com/)
  - Hosted on [Vercel](https://vercel.com/)

- **Backend**:
  - [FastAPI](https://fastapi.tiangolo.com/)

- **Model**:
  - [YOLO v8s](https://github.com/ultralytics/ultralytics)
  - [Indian Road Traffic Sign Detection dataset](https://ieee-dataport.org/documents/irtsd-datasetv1-indian-road-traffic-sign-detection-dataset)
  - [Annotated Indian Road Traffic Sign Detection dataset on Roboflow](https://universe.roboflow.com/aaa-t4bs0/my-second-project-eby1m/dataset/4)

## Getting Started

### Prerequisites

- **[Node.js](https://nodejs.org)** (v14 or above)
- **[Python](https://www.python.org/)** (v3.8 or above)
- **[Git](https://git-scm.com/)**

### Frontend Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Signalyze/www.git
   cd www
   ```

2. **Install dependencies and run the developement server**:
   ```bash
   npm install
   npm run dev
   ```
   Open [localhost:3000](http://localhost:3000) to view it in your browser.

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
   The API will be available at [localhost:8000](http://localhost:8000). Configure this as the API URL on the frontend.

## Contributing

We welcome contributions from the community! If you would like to contribute to Signalyze, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes with clear and descriptive messages.
4. Submit a pull request detailing your changes.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions, feedback, or support, please create an issue at the respective repository.

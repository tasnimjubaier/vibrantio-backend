# Vibrantio - Backend

### Description
This is the backend API for **Vibrantio**, a platform that enhances engagement and morale for remote teams. Built with **Node.js** and **Express**, this API uses **AWS Cognito** for authentication and **DynamoDB** for data storage.

### Project Structure
- **Express** - Framework for building API endpoints.
- **AWS SDK** - Integrates with AWS Cognito for authentication and DynamoDB for data storage.
- **Docker** - The backend is containerized for easy deployment on AWS EC2.

### Features
- **User Authentication** - Secure authentication and session management with AWS Cognito.
- **Recognition System** - API endpoints for creating and retrieving recognitions.
- **Wellness Check-Ins** - Endpoints for submitting and viewing check-ins.
- **Engagement Analytics** - Data aggregation endpoints for team engagement insights.

### Getting Started

#### Prerequisites
- Node.js (v14+)
- Docker (for local containerized deployment)

#### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/vibrantio-backend.git
   cd vibrantio-backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory with the following:
     ```env
     AWS_REGION=your-aws-region
     COGNITO_USER_POOL_ID=your-cognito-user-pool-id
     COGNITO_APP_CLIENT_ID=your-cognito-app-client-id
     DYNAMODB_TABLE_USERS=users-table-name
     DYNAMODB_TABLE_RECOGNITIONS=recognitions-table-name
     DYNAMODB_TABLE_CHECKINS=checkins-table-name
     ```

#### Running the Server Locally
To start the server locally:
```bash
npm run dev
```
The server will run at [http://localhost:3000](http://localhost:3000).

#### Docker Setup
To run the backend with Docker:
1. Build the Docker image:
   ```bash
   docker build -t vibrantio-backend .
   ```
2. Run the container:
   ```bash
   docker run -p 3000:3000 vibrantio-backend
   ```

### API Endpoints

#### Authentication (AWS Cognito Middleware)
- **POST /auth/login** - Log in users and verify with AWS Cognito.
- **POST /auth/signup** - Register new users through Cognito.

#### Recognitions
- **POST /recognitions** - Submit a recognition.
- **GET /recognitions** - Retrieve recent recognitions.

#### Check-Ins
- **POST /checkins** - Submit a new check-in.
- **GET /checkins** - Retrieve recent check-ins.

#### Analytics
- **GET /analytics/checkin-trends** - Aggregate check-in data.
- **GET /analytics/top-recognitions** - Get summary of top recognitions.

### Deployment
For deployment, we recommend using **AWS EC2** with Docker or **AWS Elastic Beanstalk** for managed scaling. The backend will also work well in a serverless configuration with **AWS Lambda**.

### Contributing
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Make your changes and commit (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Open a Pull Request.

### License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

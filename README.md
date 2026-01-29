# DevTinder - A Tinder Clone for Developers

DevTinder is a full-stack web application that replicates the core functionality of Tinder, specifically designed for developers to connect with other developers. It includes features like user authentication, connection requests, messaging, and payment integration.

## Features

- **User Authentication**: Secure signup and login with JWT authentication
- **Profile Management**: Create and edit user profiles with profile pictures
- **Connection Requests**: Send and receive connection requests
- **Real-time Chat**: Live messaging with other connected users using WebSockets
- **Payment Integration**: Integrated Razorpay payment gateway for premium features
- **Email Notifications**: Automated email notifications for important events
- **Validation**: Comprehensive input validation and security measures

## Tech Stack

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Real-time Communication**: Socket.IO
- **Payment Gateway**: Razorpay
- **Email Service**: AWS SES
- **Scheduled Tasks**: Node Cron

### Frontend
- Built with modern web technologies
- Real-time updates via WebSockets

## Project Structure

```
src/
├── app.js                 # Main Express application
├── config/
│   └── database.js        # MongoDB connection configuration
├── middlewares/
│   └── auth.js           # JWT authentication middleware
├── models/
│   ├── user.js           # User schema and model
│   ├── connectionRequest.js # Connection request schema
│   ├── chat.js           # Chat message schema
│   └── payment.js        # Payment schema
├── routes/
│   ├── auth.js           # Authentication routes
│   ├── user.js           # User profile routes
│   ├── request.js        # Connection request routes
│   ├── chat.js           # Chat routes
│   ├── payment.js        # Payment routes
│   └── profile.js        # Profile routes
└── utils/
    ├── validation.js     # Input validation utilities
    ├── constants.js      # Application constants
    ├── sendEmail.js      # Email sending utilities
    ├── sesClient.js      # AWS SES client configuration
    ├── razorpay.js       # Razorpay payment utilities
    ├── socket.js         # Socket.IO configuration
    └── cronjob.js        # Scheduled tasks
```

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- npm or yarn

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/kundan13shinde-bot/Tinderdev.git
   cd Tinderdev
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   Create a `.env` file in the root directory with the following variables:
   ```
   PORT=7777
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   RAZORPAY_KEY_ID=your_razorpay_key
   RAZORPAY_KEY_SECRET=your_razorpay_secret
   AWS_SES_REGION=your_aws_region
   AWS_ACCESS_KEY_ID=your_aws_access_key
   AWS_SECRET_ACCESS_KEY=your_aws_secret_key
   ```

4. **Start the application**
   ```bash
   npm start
   ```
   The server will run on `http://localhost:7777`

## API Endpoints

### Authentication
- `POST /auth/signup` - Register a new user
- `POST /auth/login` - Login user
- `POST /auth/logout` - Logout user

### User Profile
- `GET /profile` - Get user profile
- `PATCH /profile/edit` - Update user profile

### Connection Requests
- `POST /request/send/:userId` - Send connection request
- `POST /request/review/:requestId` - Accept or reject request
- `GET /request/received` - Get received connection requests
- `GET /user/connections` - Get all connections

### Chat
- `GET /chat/:userId` - Get chat history with a user
- `POST /chat/send` - Send a message

### Payments
- `POST /payment/create-order` - Create payment order
- `POST /payment/verify` - Verify payment

## Real-time Features

The application uses Socket.IO for real-time features:
- Live chat notifications
- Real-time connection status
- Instant message delivery

## Security Features

- JWT-based authentication
- Password hashing
- Input validation and sanitization
- CORS protection
- Rate limiting
- Secure session management

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Author

**Kundan Shinde**
- GitHub: [@kundan13shinde-bot](https://github.com/kundan13shinde-bot)

## Support

For support and questions, please open an issue on the GitHub repository.

---

**Note**: This is a development project. For production use, ensure all security best practices are implemented and environment variables are properly configured.

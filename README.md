# 🚀 SpeedType Master

A modern, real-time multiplayer typing game built with Node.js, WebSockets, and MySQL. Test and improve your typing speed with friends in competitive multiplayer rooms or practice solo.

## 🌟 Features

### 🎮 Game Modes
- **Single Player Mode**: Practice typing with different difficulty levels
- **Multiplayer Mode**: Compete with friends in real-time typing races
- **Room-based System**: Create private rooms or join existing ones

### 🔐 User Authentication
- Secure user registration and login
- JWT-based authentication
- Email verification with OTP
- Password reset functionality
- Persistent user sessions

### 💬 Real-time Features
- **Live Chat**: Communicate with other players in multiplayer rooms
- **Real-time Progress**: See other players' typing progress live
- **WebSocket Integration**: Instant updates and seamless multiplayer experience
- **Live WPM Tracking**: Real-time words per minute calculation

### 📊 Performance Tracking
- Words Per Minute (WPM) calculation
- Accuracy percentage
- Real-time statistics
- Completion rankings
- Performance charts and graphs

### 🎨 Modern UI/UX
- Responsive design for all devices
- Animated particles background
- Virtual keyboard highlighting
- Modern gradient aesthetics
- Mobile-friendly interface

## 🛠️ Tech Stack

### Backend
- **Node.js** - Server runtime
- **Express.js** - Web framework
- **WebSocket (ws)** - Real-time communication
- **MySQL2** - Database management
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **Nodemailer** - Email functionality

### Frontend
- **Vanilla JavaScript** - Client-side logic
- **HTML5/CSS3** - Structure and styling
- **Particles.js** - Animated backgrounds
- **Chart.js** - Performance visualization
- **WebSocket API** - Real-time updates

### Database
- **MySQL** - Primary database
- User management
- Session storage
- Game statistics

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MySQL database
- SMTP email service (for OTP verification)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/VAIBHAV13S/racetyper.git
   cd racetyper
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   # Database Configuration
   DB_HOST=your_mysql_host
   DB_USER=your_mysql_username
   DB_PASSWORD=your_mysql_password
   DB_NAME=your_database_name
   DB_PORT=3306

   # JWT Secret
   JWT_SECRET=your_super_secret_jwt_key

   # Email Configuration (for OTP)
   SMTP_HOST=your_smtp_host
   SMTP_PORT=587
   SMTP_USER=your_email@domain.com
   SMTP_PASS=your_email_password
   EMAIL_FROM=your_email@domain.com

   # Server Configuration
   PORT=3000
   NODE_ENV=production
   ```

4. **Set up the database**
   
   The application will automatically create the required tables on startup:
   ```sql
   CREATE TABLE IF NOT EXISTS users (
       id INT NOT NULL AUTO_INCREMENT,
       name VARCHAR(255),
       email VARCHAR(255) UNIQUE,
       password VARCHAR(255),
       PRIMARY KEY (id)
   );
   ```

5. **Start the application**
   ```bash
   npm start
   ```

6. **Access the application**
   - Local: http://localhost:3000
   - Production: https://your-domain.com

## 📱 Usage

### For Players

1. **Sign Up**: Create an account with email verification
2. **Choose Mode**: 
   - Single Player: Practice alone with different difficulty levels
   - Multiplayer: Join or create rooms to play with friends
3. **Start Typing**: Follow the text and track your performance
4. **View Results**: See your WPM, accuracy, and ranking

### For Room Hosts

1. **Create Room**: Generate a unique room ID
2. **Share Room ID**: Invite friends using the room code
3. **Start Game**: Begin the typing race when all players are ready
4. **Monitor Progress**: Watch live progress of all participants

## 🔧 API Endpoints

### Authentication
- `POST /signup` - User registration
- `POST /verify-otp` - Email verification
- `POST /login` - User login
- `GET /dashboard` - Protected user dashboard
- `POST /forgetpass` - Password reset request
- `POST /changePass` - Update password

### Health Check
- `GET /health` - Server status and configuration check

## 🌐 Deployment

### Environment Setup

The application is deployed on Render.com. Key deployment considerations:

1. **Environment Variables**: Ensure all required environment variables are set
2. **Database**: Use a cloud MySQL service (e.g., PlanetScale, AWS RDS)
3. **Email Service**: Configure SMTP (Gmail, SendGrid, etc.)
4. **WebSocket**: Ensure WebSocket connections are supported

### Production Configuration

```javascript
// WebSocket connection for production
const wsProtocol = window.location.protocol === 'https:' ? 'wss:' : 'ws:';
const wsHost = window.location.host;
const ws = new WebSocket(`${wsProtocol}//${wsHost}`);
```

## 🏗️ Architecture

### Server Structure
```
server.js              # Main server file
├── middleware/
│   └── auth.js        # JWT authentication middleware
├── public/            # Static frontend files
│   ├── mainpage/      # Landing page
│   ├── signIn/        # Authentication pages
│   ├── singlePlayer/  # Solo typing game
│   ├── multiplayer/   # Multiplayer game
│   └── room_making/   # Room management
```

### Real-time Communication
- **WebSocket Events**: User progress, chat messages, room management
- **Room Management**: Dynamic room creation and joining
- **Live Updates**: Real-time WPM, progress bars, completion status

### Database Schema
```sql
users
├── id (INT, AUTO_INCREMENT, PRIMARY KEY)
├── name (VARCHAR(255))
├── email (VARCHAR(255), UNIQUE)
└── password (VARCHAR(255), HASHED)
```

## 🧪 Testing

### Health Check
Visit `/health` endpoint to verify:
- Server status
- Database connection
- Email configuration

### Manual Testing
1. Create multiple browser windows
2. Sign up different users
3. Create a multiplayer room
4. Test real-time features

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Failed**
   - Verify MySQL credentials in `.env`
   - Check database server status
   - Ensure database exists

2. **Email OTP Not Sending**
   - Verify SMTP configuration
   - Check email service authentication
   - Review spam/junk folders

3. **WebSocket Connection Issues**
   - Ensure WebSocket support on hosting platform
   - Check for firewall/proxy restrictions
   - Verify WebSocket URL protocol (ws/wss)

4. **JWT Token Errors**
   - Verify JWT_SECRET is set
   - Check token expiration
   - Clear browser localStorage

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Particles.js** for animated backgrounds
- **Chart.js** for performance visualization
- **WebSocket** for real-time communication
- **Express.js** community for excellent documentation

## 📞 Support

For support, email [your-email@domain.com] or create an issue in the GitHub repository.

## 🚀 Live Demo

Visit the live application: [https://racetyper.onrender.com](https://racetyper.onrender.com)

---

**Made with ❤️ by the SpeedType Master Team**

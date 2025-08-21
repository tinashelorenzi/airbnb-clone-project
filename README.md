# AirBnB Clone Project

## Overview

This is a full-stack web application that replicates the core functionality of AirBnB, allowing users to list, discover, and book accommodations. The project is built using modern web technologies and follows best practices for scalable web development.

## Project Goals

- **User Authentication**: Secure user registration and login system
- **Property Management**: Allow hosts to create, edit, and manage property listings
- **Search & Discovery**: Enable users to search for properties with filters
- **Booking System**: Implement a reservation system with availability tracking
- **Reviews & Ratings**: Allow guests to leave reviews and ratings for properties
- **Responsive Design**: Ensure the application works seamlessly across all devices
- **Real-time Features**: Implement real-time messaging and notifications

## Tech Stack

### Frontend
- **React.js** - Modern JavaScript library for building user interfaces
- **TypeScript** - Type-safe JavaScript for better development experience
- **Tailwind CSS** - Utility-first CSS framework for rapid UI development
- **React Router** - Client-side routing for single-page application
- **Axios** - HTTP client for API communication

### Backend
- **Node.js** - JavaScript runtime for server-side development
- **Express.js** - Web application framework for Node.js
- **MongoDB** - NoSQL database for flexible data storage
- **Mongoose** - MongoDB object modeling for Node.js
- **JWT** - JSON Web Tokens for secure authentication

### Development Tools
- **Git** - Version control system
- **GitHub** - Code repository and collaboration platform
- **ESLint** - Code linting for JavaScript/TypeScript
- **Prettier** - Code formatting
- **Jest** - Testing framework

## Project Structure

```
airbnb-clone-project/
├── frontend/          # React frontend application
├── backend/           # Node.js backend API
├── docs/             # Project documentation
├── README.md         # Project overview
└── .gitignore        # Git ignore rules
```

## Team Roles

### Tinashe Matanda - Full Stack Software Developer
- **Role**: Sole developer responsible for the entire AirBnB Clone project
- **Responsibilities**: 
  - Frontend development (React.js, TypeScript, Tailwind CSS)
  - Backend development (Node.js, Express.js, MongoDB)
  - Database design and management
  - UI/UX design and implementation
  - Testing and quality assurance
  - Deployment and DevOps
  - Project planning and documentation
- **Key Tasks**: 
  - End-to-end feature development
  - Code review and optimization
  - Technical documentation
  - Testing and bug fixes
  - Performance optimization
  - Security implementation
- **Skills**: Full-stack development, React.js, Node.js, MongoDB, TypeScript, Tailwind CSS, API design, database management, testing, deployment, and project management

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager
- MongoDB (local or cloud instance)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/airbnb-clone-project.git
   cd airbnb-clone-project
   ```

2. Install dependencies:
   ```bash
   # Install backend dependencies
   cd backend
   npm install
   
   # Install frontend dependencies
   cd ../frontend
   npm install
   ```

3. Set up environment variables:
   ```bash
   # Backend .env
   cp backend/.env.example backend/.env
   
   # Frontend .env
   cp frontend/.env.example frontend/.env
   ```

4. Start the development servers:
   ```bash
   # Start backend server
   cd backend
   npm run dev
   
   # Start frontend server (in a new terminal)
   cd frontend
   npm start
   ```

## Features

- [ ] User authentication and authorization
- [ ] Property listing creation and management
- [ ] Advanced search and filtering
- [ ] Booking and reservation system
- [ ] Real-time messaging
- [ ] Review and rating system
- [ ] Payment integration
- [ ] Admin dashboard
- [ ] Mobile responsive design

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by AirBnB's user experience and functionality
- Built with modern web development best practices
- Special thanks to the open-source community for the amazing tools and libraries
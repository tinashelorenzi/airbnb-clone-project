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

## Database Design

### Key Entities

#### Users
- **id**: Unique identifier for each user
- **email**: User's email address (unique)
- **password**: Hashed password for authentication
- **firstName**: User's first name
- **lastName**: User's last name
- **phoneNumber**: Contact phone number
- **profileImage**: URL to user's profile picture
- **isHost**: Boolean indicating if user is a property host
- **createdAt**: Timestamp when account was created
- **updatedAt**: Timestamp of last profile update

#### Properties
- **id**: Unique identifier for each property
- **title**: Property listing title
- **description**: Detailed property description
- **address**: Property location address
- **city**: City where property is located
- **country**: Country where property is located
- **price**: Nightly rental price
- **bedrooms**: Number of bedrooms
- **bathrooms**: Number of bathrooms
- **maxGuests**: Maximum number of guests allowed
- **amenities**: Array of available amenities
- **images**: Array of property image URLs
- **hostId**: Reference to the user who owns the property
- **isAvailable**: Boolean indicating if property is available for booking
- **createdAt**: Timestamp when listing was created
- **updatedAt**: Timestamp of last listing update

#### Bookings
- **id**: Unique identifier for each booking
- **propertyId**: Reference to the booked property
- **guestId**: Reference to the user making the booking
- **hostId**: Reference to the property owner
- **checkInDate**: Date when guest will check in
- **checkOutDate**: Date when guest will check out
- **totalPrice**: Total cost for the entire stay
- **numberOfGuests**: Number of guests for this booking
- **status**: Booking status (pending, confirmed, cancelled, completed)
- **createdAt**: Timestamp when booking was created
- **updatedAt**: Timestamp of last booking update

#### Reviews
- **id**: Unique identifier for each review
- **propertyId**: Reference to the reviewed property
- **guestId**: Reference to the user who wrote the review
- **hostId**: Reference to the property owner
- **rating**: Numerical rating (1-5 stars)
- **comment**: Text review content
- **cleanliness**: Rating for cleanliness
- **communication**: Rating for host communication
- **checkIn**: Rating for check-in experience
- **accuracy**: Rating for listing accuracy
- **location**: Rating for location
- **value**: Rating for value for money
- **createdAt**: Timestamp when review was created

#### Payments
- **id**: Unique identifier for each payment
- **bookingId**: Reference to the associated booking
- **guestId**: Reference to the user making the payment
- **hostId**: Reference to the property owner receiving payment
- **amount**: Payment amount
- **currency**: Payment currency (e.g., USD, EUR)
- **paymentMethod**: Method used for payment (credit card, PayPal, etc.)
- **status**: Payment status (pending, completed, failed, refunded)
- **transactionId**: External payment processor transaction ID
- **createdAt**: Timestamp when payment was processed

### Entity Relationships

- **Users → Properties**: One-to-Many relationship - A user (host) can have multiple properties
- **Users → Bookings**: One-to-Many relationship - A user can make multiple bookings as a guest
- **Properties → Bookings**: One-to-Many relationship - A property can have multiple bookings (at different times)
- **Properties → Reviews**: One-to-Many relationship - A property can have multiple reviews from different guests
- **Bookings → Reviews**: One-to-One relationship - Each booking can have one review (after completion)
- **Bookings → Payments**: One-to-One relationship - Each booking has one associated payment
- **Users → Reviews**: One-to-Many relationship - A user can write multiple reviews for different properties

### Database Schema Overview

```
Users {
  id: ObjectId
  email: String (unique)
  password: String (hashed)
  firstName: String
  lastName: String
  phoneNumber: String
  profileImage: String
  isHost: Boolean
  createdAt: Date
  updatedAt: Date
}

Properties {
  id: ObjectId
  title: String
  description: String
  address: String
  city: String
  country: String
  price: Number
  bedrooms: Number
  bathrooms: Number
  maxGuests: Number
  amenities: [String]
  images: [String]
  hostId: ObjectId (ref: Users)
  isAvailable: Boolean
  createdAt: Date
  updatedAt: Date
}

Bookings {
  id: ObjectId
  propertyId: ObjectId (ref: Properties)
  guestId: ObjectId (ref: Users)
  hostId: ObjectId (ref: Users)
  checkInDate: Date
  checkOutDate: Date
  totalPrice: Number
  numberOfGuests: Number
  status: String
  createdAt: Date
  updatedAt: Date
}

Reviews {
  id: ObjectId
  propertyId: ObjectId (ref: Properties)
  guestId: ObjectId (ref: Users)
  hostId: ObjectId (ref: Users)
  rating: Number
  comment: String
  cleanliness: Number
  communication: Number
  checkIn: Number
  accuracy: Number
  location: Number
  value: Number
  createdAt: Date
}

Payments {
  id: ObjectId
  bookingId: ObjectId (ref: Bookings)
  guestId: ObjectId (ref: Users)
  hostId: ObjectId (ref: Users)
  amount: Number
  currency: String
  paymentMethod: String
  status: String
  transactionId: String
  createdAt: Date
}
```

## Feature Breakdown

### User Management
The user management system handles user registration, authentication, and profile management. Users can create accounts, log in securely using JWT tokens, and maintain their profiles with personal information and preferences. This feature also includes role-based access control, distinguishing between regular users and property hosts.

### Property Management
Property management allows hosts to create, edit, and manage their property listings with detailed information including descriptions, photos, amenities, and pricing. Hosts can update availability calendars, modify property details, and view booking requests for their properties. This feature provides a comprehensive dashboard for hosts to manage multiple properties efficiently.

### Search & Discovery
The search and discovery feature enables users to find properties based on location, dates, price range, and specific amenities. Advanced filtering options include property type, number of bedrooms, and guest capacity. The system provides real-time search results with property previews and availability indicators to help users make informed decisions.

### Booking System
The booking system manages the entire reservation process from initial request to confirmation. Users can select check-in and check-out dates, specify guest count, and view total pricing including fees. The system handles booking conflicts, sends confirmation emails, and maintains booking history for both guests and hosts.

### Review & Rating System
The review and rating system allows guests to provide feedback on their stay experience with detailed ratings across multiple categories (cleanliness, communication, check-in, accuracy, location, and value). These reviews help future guests make informed decisions and provide hosts with valuable feedback to improve their listings.

### Payment Integration
Payment integration securely processes transactions using popular payment gateways like Stripe or PayPal. The system handles payment processing, refunds, and maintains transaction records. It supports multiple currencies and payment methods while ensuring PCI compliance and secure data handling.

### Real-time Messaging
Real-time messaging enables direct communication between guests and hosts through an instant messaging system. Users can discuss booking details, ask questions about properties, and coordinate check-in arrangements. The messaging system includes notifications and message history for seamless communication.

### Admin Dashboard
The admin dashboard provides comprehensive oversight of the platform with analytics, user management, and system monitoring capabilities. Administrators can view platform statistics, manage user accounts, moderate content, and handle disputes. This feature ensures platform integrity and provides insights for business decisions.

### Mobile Responsive Design
Mobile responsive design ensures the application works seamlessly across all devices and screen sizes. The interface adapts to different screen resolutions, providing an optimal user experience on smartphones, tablets, and desktop computers. This feature is essential for modern web applications where users access services from various devices.

### Notification System
The notification system keeps users informed about important events such as booking confirmations, payment receipts, and message alerts. Notifications are delivered through multiple channels including email, in-app notifications, and push notifications for mobile devices. This feature enhances user engagement and ensures timely communication.

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
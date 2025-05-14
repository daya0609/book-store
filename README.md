# Book Store RESTful API

Welcome! This is a simple, beginner-friendly RESTful API for a bookstore, built with Express and MongoDB. It lets you register, log in, browse books, and place orders. Admins can manage the book inventory. Everything is protected with authentication, rate limiting, and clear error messages.

## Features
- Easy Registration & Login: Secure passwords (bcrypt) and JWT tokens for safe access
- Role-based Access:
  - Regular users: Browse and order books
  - Admins: Add, update, and delete books
- Book Management: Admins can fully manage the book list
- Order System: Users can place and view their own orders
- Fair Use: Each user gets 100 requests per hour (rate limiting)
- Helpful Errors: Centralized error handler for clear feedback

## API Endpoints

Base URL: http://localhost:3000

### Auth
- `POST http://localhost:3000/register` — Create a new user (name, email, password, role)
- `POST http://localhost:3000/login` — Log in and get your JWT token

### Books
- `GET http://localhost:3000/books` — See all books (login required)
- `POST http://localhost:3000/books` — Add a book (admin only)
- `PUT http://localhost:3000/books/:id` — Update a book (admin only)
- `DELETE http://localhost:3000/books/:id` — Remove a book (admin only)

### Orders
- `POST http://localhost:3000/orders` — Place an order (login required)
- `GET http://localhost:3000/orders` — See your orders (login required)

## How to Use
1. Install dependencies:
   ```sh
   npm install
   ```
2. Start MongoDB (make sure it's running locally on port 27017)
3. Run the server:
   ```sh
   npm start
   ```
4. Try the API! Use Postman, Insomnia, or curl. For protected routes, add your JWT token in the header:
   ```
   Authorization: Bearer <your_token>
   ```

## User Roles
- `user`: Can browse books and place orders
- `admin`: Can manage all books (add, edit, delete)

## Tech Stack
- Node.js + Express
- MongoDB + Mongoose
- JWT for authentication
- bcrypt for password security

## Notes
- Rate limiting is in-memory (per user, resets every hour)
- For real-world use, store secrets in environment variables and consider Redis for distributed rate limiting

---

Happy coding and enjoy your bookstore API!

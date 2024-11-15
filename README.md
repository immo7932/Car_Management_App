## Project Overview

This project is a **Car Management Web Application** that allows users to manage their car listings. Users can register, log in, add new cars with details and images, edit existing car information, and delete cars. The application is built with **React** for the frontend and **Express.js** with **MongoDB** for the backend. It features secure authentication, image upload functionality, and a responsive user interface.

---

## Table of Contents

- [Live Demo](#live-demo)
- [Project Report](#project-report)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [Deployment](#deployment)
- [Assumptions and Limitations](#assumptions-and-limitations)
- [Special Instructions](#special-instructions)
- [Dependencies](#dependencies)
- [Additional Notes](#additional-notes)

---

## Live Demo

Access the live versions of the frontend and backend applications through the links below:

- **Deployed Application**: [Car Management Frontend](https://car-frontend-h6g5.onrender.com/)

---

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Node.js** and **npm** installed on your machine. You can download them from the [Node.js Official Website](https://nodejs.org/).
- **MongoDB** installed locally or a cloud-based MongoDB Atlas cluster.
- **Git** installed for version control (optional but recommended).

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/yourusername/car-management-app.git
```

### Navigate to the Project Directory

```bash
cd car-management-app
```

### Install Dependencies for Backend

```bash
cd backend
npm install
```

### Install Dependencies for Frontend

```bash
cd ../frontend
npm install
```

---

## Running the Application

### Backend

1. **Configure Environment Variables**:

   Create a `.env` file in the `backend` directory with the following variables:

   ```env
   PORT=5000
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   ```

2. **Start the Backend Server**:

   ```bash
   cd backend
   npm start
   ```

   The backend API will run on `http://localhost:5000`.

### Frontend

1. **Configure Environment Variables**:

   Create a `.env` file in the `frontend` directory with the following variable:

   ```env
   REACT_APP_API_BASE_URL=http://localhost:5000
   ```

2. **Start the Frontend Application**:

   ```bash
   cd frontend
   npm start
   ```

   The frontend application will start on `http://localhost:3000` by default.

---

## Project Structure

### Frontend (`frontend/`)

```
src/
├── components/
│   ├── Auth/
│   │   ├── Login.js
│   │   ├── Signup.js
│   │   └── AuthContext.js
│   ├── Cars/
│   │   ├── CarList.js
│   │   ├── CarDetail.js
│   │   └── CarForm.js
│   ├── Layout/
│   │   └── Navbar.js
│   └── App.js
├── assets/
│   └── styles/
│       ├── Login.css
│       ├── Signup.css
│       ├── Navbar.css
│       ├── CarList.css
│       ├── CarDetail.css
│       └── CarForm.css
├── index.js
└── package.json
```

### Backend (`backend/`)

```
src/
├── controllers/
│   ├── authController.js
│   └── carController.js
├── middleware/
│   └── auth.js
├── models/
│   ├── User.js
│   └── Car.js
├── routes/
│   ├── auth.js
│   └── cars.js
├── uploads/
│   └── (uploaded images)
├── app.js
├── server.js
├── config/
│   └── db.js
└── package.json
```

---

## Deployment

The application can be deployed using platforms like **Render.com**. Below are the steps to deploy both the frontend and backend applications.

### Frontend Deployment

1. **Connect Repository**:

   - Log in to your deployment platform and connect your GitHub repository.

2. **Create a New Project**:

   - Select the `frontend` directory.
   - Set the build command to `npm run build`.
   - Set the publish directory to `build`.

3. **Environment Variables**:

   - Set `REACT_APP_API_BASE_URL` to your backend API URL.

4. **Deploy**:

   - The platform will automatically build and deploy your frontend application.

### Backend Deployment

1. **Connect Repository**:

   - Log in to your deployment platform and connect your GitHub repository.

2. **Create a New Project**:

   - Select the `backend` directory.
   - Set the build command to `npm install`.
   - Set the start command to `npm start`.

3. **Environment Variables**:

   - Add necessary environment variables:

     ```env
     PORT=5000
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     ```

4. **Deploy**:

   - The platform will automatically install dependencies and start your backend server.

---

## Assumptions and Limitations

- **Authentication**:

  - The application uses JWT tokens for authentication, stored securely in `localStorage`.
  - Only authenticated users can add, edit, or delete car listings.

- **Image Uploads**:

  - Users can upload up to 10 images per car.
  - Images are stored on the server in the `uploads/` directory.

- **API Endpoints**:

  - The frontend expects specific API endpoints (e.g., `/api/auth/login`, `/api/cars`).
  - Ensure these endpoints are available and correctly configured in the backend.

- **Data Validation**:

  - Basic validation is implemented for forms. Additional validation may be necessary for production.

- **CORS Configuration**:

  - The backend includes CORS settings to allow requests from the frontend application.

---

## Special Instructions

### Environment Variables

- **Security**:

  - For production, set environment variables directly in your deployment platform instead of using `.env` files.

### Image Handling

- **Static Files Serving**:

  - The backend serves static files from the `uploads/` directory.
  - Ensure that this directory exists and is correctly configured.

- **Multer Configuration**:

  - The application uses Multer for handling multipart/form-data for image uploads.

### Styling Conflicts

- **CSS Styling**:

  - The application uses modular CSS files for styling components.
  - Ensure that class names in the components match those in the CSS files.

### Error Handling

- **User Feedback**:

  - Basic error handling is implemented. Further enhancements may be necessary for a better user experience.

---

## Dependencies

### Frontend

- **React**: A JavaScript library for building user interfaces.
- **React Router DOM**: For handling routing in the application.
- **Axios**: For making HTTP requests to the backend API.

### Backend

- **Express.js**: A fast, unopinionated, minimalist web framework for Node.js.
- **MongoDB & Mongoose**: For database management.
- **Multer**: For handling file uploads.
- **bcryptjs**: For hashing passwords.
- **jsonwebtoken**: For handling JWT tokens.
- **dotenv**: For loading environment variables.
- **cors**: For enabling Cross-Origin Resource Sharing.
- **Body-Parser**: For parsing incoming request bodies.

### Other Tools

- **Nodemon**: For automatically restarting the server during development.

For a complete list of dependencies and their versions, refer to the respective `package.json` files in the `frontend` and `backend` directories.

---

## Additional Notes

### Responsive Design

- The application is responsive and displays well on various screen sizes due to the use of modular CSS and responsive units.

### Image Size Limitations

- Images uploaded are limited in size to prevent excessive storage use.
- Frontend components limit the display size of images for consistent layout.

### Security Best Practices

- **Input Validation**: Ensure all user inputs are validated on both the frontend and backend.
- **Authentication**: Routes are protected using authentication middleware.
- **Error Messages**: Avoid exposing sensitive information in error messages.

### Regularly Update Dependencies

- Keep your dependencies up-to-date to benefit from security patches and new features.

### Code Consistency

- **Code Formatting**: Use tools like Prettier and ESLint to maintain code consistency.
- **Comments**: Comment your code where necessary to explain complex logic.

---


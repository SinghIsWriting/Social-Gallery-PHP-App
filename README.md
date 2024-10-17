# Social Gallery

A feature-rich social media web application where users can upload and share images, like, comment, and interact with others in a visual gallery. Registered users can connect with each other, share their work, and communicate via a contact form. The project is built using PHP, MySQL, and JavaScript, with a responsive design for modern web browsers.

## Deployed Project Link [Click Here](http://pal-pal-pal.wuaze.com/social-gallery/)
### Home Page
![S1](https://github.com/user-attachments/assets/ccc273cc-0571-4b87-831a-acd07feea4c7)

### Detail View Page
![S22](https://github.com/user-attachments/assets/6ab9b4c9-397d-433f-ab90-cc163e29c5e0)

## Table of Contents
- [Features](#features)
- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Clone the Repository](#clone-the-repository)
  - [Setup](#setup)
  - [Database Setup](#database-setup)
  - [Run the Application](#run-the-application)
- [Usage](#usage)
- [Technology Stack](#technology-stack)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- **User Authentication**: Registration and login with password hashing.
- **Image Upload**: Users can upload images and create their own galleries.
- **Social Interactions**: Users can like and comment on images posted by others.
- **Contact Form**: Registered users can send messages via the contact form, with email verification.
- **Responsive Design**: Mobile-first layout that adapts to various screen sizes.
- **Image Management**: Ability to view and delete uploaded images.
- **Secure Form Submissions**: CSRF protection for forms and validation for user input.
- **Database Integration**: MySQL-powered backend for managing users, images, likes, and comments.

## Installation

Follow these steps to set up the project on your local machine.

### Prerequisites

- **PHP 7.4+**
- **MySQL/MariaDB**
- **Composer** (for managing PHP dependencies)
- **XAMPP/WAMP** or similar web server environment
- **Git** (optional but recommended)

### Clone the Repository

To start, clone the repository from GitHub:

```bash
git clone https://github.com/SinghIsWriting/Social-Gallery-PHP-App.git
cd Social-Gallery-PHP-App
```

### Setup
* Install Dependencies
Open a terminal in your project directory and run:
```
composer install
```
This will install all the necessary dependencies listed in composer.json.

* Create an `.env` File
Copy the .env.example file (if it exists) or create a new .env file in the root of your project directory:
```
cp .env.example .env
```
Open the .env file and fill in your database and other credentials:
```
DB_HOST=localhost
DB_USERNAME=root
DB_PASSWORD=
DB_DATABASE=social_gallery
DB_PORT=3306
```

* Load Environment Variables in PHP
Make sure your project is loading the .env file using vlucas/phpdotenv. Check the db_connect.php file to ensure that environment variables are correctly accessed (see previous steps for loading .env).

### Database Setup

* Ensure MySQL Apache is running (e.g., through XAMPP or WAMP).
* Access `http://localhost/phpmyadmin` and login.
* Create the database in MySQL:
```
CREATE DATABASE social_gallery;
```
* Create required tables to store data using following sql commands:
```
-- Add Users table
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Add images table
CREATE TABLE images (
  id int(11) NOT NULL,
  user_id INT NOT NULL,
  description text DEFAULT NULL,
  image_path varchar(255) NOT NULL,
  uploaded_on timestamp NOT NULL DEFAULT current_timestamp(),
  FOREIGN KEY (user_id) REFERENCES users(id)
);

-- Add likes table
CREATE TABLE likes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    image_id INT NOT NULL,
    user_id INT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (image_id) REFERENCES images(id),
    FOREIGN KEY (user_id) REFERENCES users(id),
    UNIQUE KEY unique_like (image_id, user_id)
);

-- Add comments table
CREATE TABLE comments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    image_id INT NOT NULL,
    user_id INT NOT NULL,
    comment TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (image_id) REFERENCES images(id),
    FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE TABLE contact_us (
    id INT(11) AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    message TEXT NOT NULL,
    submission_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

ALTER TABLE contact_us ADD COLUMN registered_mail ENUM('yes', 'no') DEFAULT 'no';

```

### Run the Application
* If you are using XAMPP/WAMP, place the project folder in the htdocs directory.
* Start your Apache and MySQL servers.
* Access the project by navigating to:
```
http://localhost/Social-Gallery-PHP-App/index.php
```

## Usage
### Home Page
Once you visit the homepage, you will see the most recent gallery posts from registered users. The interface is designed to allow users to view, like, and comment on images.

### User Registration & Login
* New users can sign up by filling out the registration form.
* Existing users can log in using their email and password.

### Uploading Images
After logging in, users can upload images to their profile, which will be displayed in the gallery. Each image can be liked or commented on by other users.

### Liking & Commenting
* Liking: Click the heart icon to like an image.
* Commenting: Use the comment icon to add a comment under an image.

### Contact Us
* Users can send a message through the Contact Us form.
* If the user’s email is registered in the system, it will be marked as a registered email in the database.

### Technology Stack
* Front-end: HTML5, CSS3, JavaScript (FontAwesome icons for social interaction icons)
* Back-end: PHP 7.4+
* Database: MySQL 5.7+ (or MariaDB)
* Email: PHPMailer (for SMTP functionality)
* Web Server: Apache (XAMPP or WAMP)

## Contributing
We welcome contributions from the community. If you'd like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch:
```
git checkout -b feature-branch
```
3. Commit your changes:
```
git commit -m 'Add some feature'
```
4. Push to the branch:
```
git push origin feature-branch
```
5. Open a Pull Request.
Please ensure your code follows best practices and is well documented.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact
If you have any questions or need support, feel free to contact the project maintainer:

* Email: sabhisheksignh343104@gmail.com
* GitHub: [SinghIsWriting](https://github.com/SinghIsWriting)
* LinkedIn: [Abhishek Singh](https://www.linkedin.com/in/abhishek-singh-bba2662a9)


### Breakdown of Sections:

1. **Features**: Lists the main features of the Social Gallery project.
2. **Installation**: Provides a step-by-step guide on how to set up the project locally.
3. **Usage**: Explains how users can interact with the application.
4. **Technology Stack**: Summarizes the technologies used in the project.
5. **Folder Structure**: Gives an overview of how the project is organized.
6. **Contributing**: Provides guidelines for contributing to the project.
7. **License**: Specifies the licensing terms for the project.
8. **Contact**: How to get in touch with the maintainer for questions or feedback.

Make sure to replace the placeholder URLs, emails, and other project-specific details before using this template for your project!


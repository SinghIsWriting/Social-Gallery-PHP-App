# Social Gallery

A feature-rich social media web application where users can upload and share images, like, comment, and interact with others in a visual gallery. Registered users can connect with each other, share their work, and communicate via a contact form. The project is built using PHP, MySQL, and JavaScript, with a responsive design for modern web browsers.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Clone the Repository](#clone-the-repository)
  - [Configure Environment](#configure-environment)
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

### Database Setup

1. Create a new MySQL database:
```
CREATE DATABASE picture_block;
```

### Run the Application
1. If you are using XAMPP/WAMP, place the project folder in the htdocs directory.
2. Start your Apache and MySQL servers.
3. Access the project by navigating to:
```
http://localhost/Social-Gallery-PHP-App
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
* GitHub: SinghIsWriting
* Website: www.linkedin.com/in/abhishek-singh-bba2662a9


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


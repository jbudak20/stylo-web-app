# Stylo

Welcome to Sytlo - a modern webshop built using CMS and MACH architecture.

This project was created by a team of students, including myself, as a part of course at the University of Zagreb, <a href="https://foi.unizg.hr" target="_blank">Faculty of Organization and Informatics</a>.
The project was mentored and reviewed by <a href="https://ibmix.de/en/" target="_blank">IBM iX</a> and was documented and developed using SCRUM methodology alongside Jira and Confluence tools.

![302419378-ab4b58cd-923c-498b-b930-95e9c34aebef](https://github.com/user-attachments/assets/d640764e-4f6f-43d1-a1bc-55eb47ba173b)

## Stylo documentation - table of contents

<ul>
  <li><a href="#app-overview">Application Overview and Core Functionalities</a></li>
  <li><a href="#project-showcase">Project Showcase</a></li>
  <li><a href="#devteam">Development Team</a></li>
  <li><a href="#technologies">Technologies</a></li>
  <li><a href="#architecture">Architecture</a></li>
</ul>

<div id="app-overview"></div>

## Application Overview and Core Functionalities

The Stylo application is an e-commerce platform designed to seamlessly integrate Content Management System (CMS) capabilities with e-commerce functionalities, leveraging the MACH (Microservices, API-first, Cloud-native, and Headless) architecture. The platform primarily focuses on the sale of footwear and offers tailored roles for administrators, employees, and customers, ensuring efficient operations and an optimized shopping experience.

### Employee Management Features
- Employees can oversee product listings, manage product categories, review customer order data, and update order statuses
- Through the CMS, employees can create, update, and delete web pages, ensuring a dynamic and up-to-date online presence
- Currently, administrators are responsible for adding employees to the system.

### Customer Experience and Capabilities
- Browsing and Shopping: Customers can explore categories, filter and sort products, and view detailed product pages with information such as price, images, availability, descriptions, and product names
- Purchasing: The shopping cart allows for seamless card-based transactions, with invoices automatically sent to customers via email
- Support: Customers can reach out to employees through a contact or customer support form for assistance

### Account Registration and Activation
- Unregistered users can easily register on the platform, receiving an activation email to confirm their accounts and gain full access.

<div id="project-showcase"></div>

## Project Showcase

<p align="center">
  <p>Click on the videos down below: 👇</p>
  <div style="display: flex; justify-content: center; align-items: center; gap: 40px;">
    <a href="https://youtu.be/VIzjsMCsqaA?si=7Xju6KpGcK5kkK07" style="text-decoration: none;">
      <img src="https://img.youtube.com/vi/VIzjsMCsqaA/hqdefault.jpg" alt="Video 1" width="400">
    </a>
    <a href="https://www.youtube.com/watch?v=Q1oDcStelPk" style="text-decoration: none;">
      <img src="https://img.youtube.com/vi/Q1oDcStelPk/hqdefault.jpg" alt="Video 2" width="400">
    </a>
  </div>
</p>

Entire blueprint and design of the application can be viewed <a href="https://www.figma.com/design/7BeMYsf9fGjBY9wMeaMKJD/AiR-projekt?node-id=0-1&p=f">here</a> (Figma).

<div id="devteam"></div>

## Development Team

| Role | Github username  |  
|---|---|
| Android, DevOps | <a href="https://github.com/Filip1402">@Filip1402</a>   | 
| Frontend, UI design | <a href="https://github.com/CroAnna">@CroAnna</a>  |   
| Frontend, UI design | <a href="https://github.com/Fr1k1">@Fr1k1</a> |  
| Backend |  @jbudak20-foi (myself, on a different account)  | 
| Backend |  <a href="https://github.com/Robert4361">@Robert4361</a> | 

<div id="technologies"></div>

## Technologies

### Frontend 🎭
- **Android/Kotlin** - Resposible for developing android native app
- **React** - A  JavaScript library for building user interfaces
- **react-loader-spinner** - A lightweight spinner component for React applications
- **react-responsive-carousel** - A responsive carousel component for React applications
- **react-toastify** - A React notification library providing customizable toast messages
- **sweetalert2** - A customizable and responsive modal library for React applications
- **yup** - A schema validation library for JavaScript objects
- **emailjs** - A library for sending emails in JavaScript applications

### Backend 🕸️
- **NodeJS** - A server-side JavaScript runtime.
- **Express** - A minimal and flexible Node.js web application framework.
- **pdfkit** - A JavaScript library for generating PDF documents

### CMS ⚙️
- **<a href="https://www.contentful.com/">Contentful</a>** - A headless Content Management System (CMS) that allows you to manage and deliver digital content across various platforms.

### E-commerce 🛒
- **<a href="https://commercetools.com/">Commercetools</a>** - A modern and flexible headless commerce platform, providing APIs for building scalable and customizable ecommerce solutions. It was used as database for all products and orders.

### Mail service ✉️
- **<a href="https://www.nodemailer.com/">Nodemailer</a>** - A powerful and easy-to-use Node.js module for sending emails, enabling seamless integration of email services in applications.

### Payment 💵
- **<a href="https://stripe.com/en-hr">Stripe</a>** -A payment processing platform, facilitating secure and efficient online transactions.

### DevOps 🐟
- **<a href="https://www.docker.com/">Docker</a>** - Enables streamlined deployment by encapsulating microservices and the API gateway in portable containers, allowing for simultaneous and efficient start-up.

### API gateway 🛜
- **<a href="https://konghq.com/products/kong-gateway">Kong</a>** - An open-source API gateway that manages, secures, and scales API requests, providing a centralized point for controlling and monitoring API traffic.
The API gateway acts as a middleware connecting the frontend and backend. Its primary role is to route traffic to designated microservices, handling authentication and rate limitation to free up microservices for core business logic. Deployment in Docker and maintaining a dedicated repository are recommended practices.

<div id="architecture"></div>

## Architecture

Application is composed of 3 parts:
<ul>
  <li> Web app frontend: the main UI of the app</li>
   <li> Native android app: MVP version of web app that has modular login and registration that was required by FOI</li>
   <li> Backend: which contains 4 microservices</li>
</ul>

The backend comprises four interconnected microservices, facilitated by an API gateway such as Kong. The microservices include:
<ul>
  <li>    Products - integrates data from our headless Ecommerce and CMS APIs (products, product details, categories, webshop and homepage layout)</li>
  <li>    Receipts -  includes creation of PDF receipt which are meant to be sent to customers</li>
   <li>   Emails - used for sending mails to customers (account verfication, receiving a PDF invoice on email)</li>
   <li>   Customers - customer registration and login</li>
</ul>

Overall structure of Stylo:
<p align="center">
  <img src="https://github.com/user-attachments/assets/67684dc4-8391-4864-8381-678bf422bb86">
</p>

Structure of Stylo android application:
<p align="center">
  <img src="https://github.com/user-attachments/assets/c31683e6-a09b-4568-9b80-5c9256428103">
</p>



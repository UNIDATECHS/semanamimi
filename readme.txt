SemaNami — Digital Health Platform

SemaNami is a web‑based digital hospital and healthcare portal built with PHP, MySQL, Tailwind CSS, and JavaScript. It provides essential healthcare services including emergency requests, virtual consultations, verified staff listings, and health programs — all accessible through a modern, responsive browser interface.

The current live site is hosted at:
hSemanamimi.com

1. System Overview

Sema Nami connects patients with healthcare services. The system supports:

✔ Patient registration and login
✔ Emergency SOS requests
✔ Verified doctor and midwife listings
✔ Youth health services
✔ Newsletter subscription
✔ Interactive service cards

The frontend interface is built with modern HTML + Tailwind CSS. The backend is implemented in PHP and connects to a MySQL database.

All dynamic actions (login, emergency request, newsletter subscription, and verified staff listings) are handled by backend PHP scripts.

2. Functional Areas
🔹 User Accounts

Visitors can:

Register as a patient

Login securely

After login, session information is stored and used for backend actions (e.g., emergency request).

🔹 SOS Emergency Button

When a logged‑in user clicks SOS EMERGENCY, the system:

Sends a request to the backend.

Logs an emergency request in the database.

Returns a confirmation message.

This action is handled by:
➡ backend/emergency.php

🔹 Verified Healthcare Staff Listings

The homepage displays a list of verified health workers (doctors and midwives) fetched dynamically from the database.

Backend script:
➡ backend/verified_staff.php

Frontend displays these listings in a grid section titled “Wakunga Wenye Uzoefu (Verified)”.

🔹 Newsletter Subscription

Users can enter their email to subscribe to weekly health updates.

This action is handled by:
➡ backend/newsletter.php

🔹 Static Service Cards

Sections like:

Ambulance Request

Video Help

Nearby Health Centers

These display service prompts. Backend integration can be added later for full remote consultation and geo‑based hospital search.

3. Technology Stack
Component	Technology Used
Frontend UI	HTML, JavaScript, Tailwind CSS
CSS Icons	Font Awesome
Backend Server	PHP 8+
Database	MySQL
Dynamic Requests	AJAX / Fetch API
Session Management	PHP Sessions
Hosting	unidatechs.com
4. Database Schema

The system uses a MySQL database with the following main tables:

➤ patients

Stores patient user accounts.

Field	Type
id	INT (Primary Key)
name	VARCHAR
email	VARCHAR
password	VARCHAR (hashed)
phone	VARCHAR
created_at	TIMESTAMP
➤ doctors

Stores verified staff information.

Field	Type
id	INT (Primary Key)
name	VARCHAR
specialization	VARCHAR
email	VARCHAR
phone	VARCHAR
created_at	TIMESTAMP
➤ appointments

Records emergency or other appointments.

Field	Type
id	INT
patient_id	INT
doctor_id	INT
appointment_date	DATE
time_slot	TIME
reason	TEXT
status	ENUM
created_at	TIMESTAMP
➤ time_slots

Optional table for storing available appointment slots.

➤ patient_sessions

Optional table for storing logged‑in session tokens.

5. Important Backend Scripts
Script	Purpose
backend/db.php	Database connection
backend/login.php	Handles patient login
backend/register.php	Handles patient registration
backend/emergency.php	Logs SOS emergency requests
backend/verified_staff.php	Returns list of verified staff
backend/newsletter.php	Stores newsletter subscriptions
6. How the Frontend & Backend Work Together
✦ Login

User enters email/password.

Frontend sends data to backend/login.php.

Backend verifies credentials from patients table.

Successful login starts a session.

✦ Emergency SOS

User clicks SOS.

Frontend sends a request to backend/emergency.php.

Backend adds a record to appointments.

User sees confirmation.

✦ Verified Staff Display

Frontend loads index.php.

Server runs query from verified_staff.php.

Render doctor profiles dynamically in the UI.

✦ Newsletter Subscription

User enters email.

AJAX posts to backend/newsletter.php.

Email is stored in database.

7. How to Deploy the System

Upload frontend and backend folders to your web host.

Import the MySQL database schema into your MySQL server via phpMyAdmin or CLI.

Update backend/db.php with your database credentials.

Ensure paths are correct (frontend/index.php should reference backend scripts with correct relative paths).

Access your site at https://unidatechs.com.

8. Security & Best Practices

✔ Always hash user passwords (e.g., password_hash() in PHP).
✔ Use prepared statements to prevent SQL injection.
✔ Protect backend directories with .htaccess where needed.
✔ Ensure AJAX calls handle errors gracefully.

9. Next Steps / Enhancements

Future upgrades may include:

✅ Full remote video consultation integration
✅ Hospital geo‑location search
✅ Push notifications for quick alerts
✅ Role‑based dashboards for staff
✅ Appointment scheduling UI

10. Support & Contact

If you need help integrating or expanding the system:

📧 Contact: support@unidatechs.com


🌐 Website: https://unidatechs.com


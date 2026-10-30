# liberiaclinic-showcase

Free, secure, multi-clinic patient records for rural Liberian clinics. Documentation and screenshots only; source available on request.

<h1 align="center">LiberiaClinic</h1>
<p align="center"><b>Free digital patient records for rural clinics in Liberia, built for low connectivity.</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.0-0F6E56?style=flat-square" alt="Version"/>
  <img src="https://img.shields.io/badge/Status-Pilot%20preparation-0F6E56?style=flat-square" alt="Status"/>
  <img src="https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white" alt="Laravel"/>
  <img src="https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=pwa&logoColor=white" alt="PWA"/>
</p>

> This repository is a documentation showcase. The application source code is in a private repository
> and is available for technical review on request (see Contact).

## The problem

Most rural health facilities in Liberia still record patients on paper. Records get lost, allergies are
missed, visit history does not follow the patient, and there is no usable data for health planning.
Internet penetration is low, so any solution has to work on basic Android phones and tolerate weak connections.

## The solution

LiberiaClinic is a web-based patient records system designed for these conditions. It runs in the
browser, installs on a phone like an app, and keeps each clinic's data separate and protected.

<p align="center">
  <img src="assets/dashboard.png" width="48%" alt="Dashboard"/>
  <img src="assets/patient-profile.png" width="48%" alt="Patient profile"/>
</p>
<p align="center">
  <img src="assets/login.png" width="48%" alt="Secure login"/>
  <img src="assets/admin-panel.png" width="48%" alt="Admin panel"/>
</p>

<p align="center"><i>All screenshots use fictional demo data.</i></p>

## Features

| Area                       | What it does                                                                                         |
| -------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Patient registry**       | Demographics, village and county, blood type, known allergies, chronic conditions, emergency contact |
| **Visit logging**          | Complaint, symptoms, diagnosis, treatment, medications, vitals, follow-up date, referral             |
| **Allergy alerts**         | Automatic warning when a patient with known allergies is opened                                      |
| **Search**                 | Find patients by name, village or phone number                                                       |
| **Dashboard**              | Patients, visits, today's visits and follow-ups due, filtered to the user's clinic                   |
| **Multi-clinic isolation** | Each clinic sees only its own patients. Administrators can see all clinics                           |
| **Admin panel**            | Create clinics and staff accounts, assign staff to clinics, issue access codes, reset 2FA            |
| **PDF export**             | A full patient record with visit history in one click                                                |
| **Installable PWA**        | Installs on Android from the browser and caches pages for poor connections                           |

## Security

- Two-factor authentication: an administrator-issued 15-character access code on first login, then a
  6-digit Google Authenticator code (TOTP) for each session
- The 2FA enrolment QR code is generated on the server, so the secret is never sent to a third party
- 2FA secrets are encrypted at rest; passwords are hashed
- Public registration is disabled. Only administrators create accounts
- Database access through Laravel's Eloquent ORM with parameterised queries, plus server-side validation
- Input sanitisation middleware and hardened HTTP security headers
- CSRF protection on all forms and clinic-level access checks on patient and visit records
- Privacy Policy, Terms of Use and Cookies Policy pages. Essential cookies only, with no tracking or advertising

## Architecture

Laravel 12 (PHP 8.2) application with a MySQL database and Blade/Bootstrap 5 front end, delivered as a
Progressive Web App. A single deployment serves many clinics through a `clinic_id` on staff, patient and
visit records, and database indexes keep queries fast as data grows.

## Status

- **Built and tested locally:** version 1.0, with realistic fictional demo data for three pilot clinics
- **In preparation:** a 90-day pilot across three Liberian counties (Nimba, Lofa and Grand Bassa)
- **Not yet available:** live public deployment, and offline data entry. Version 1.0 caches the app and
  previously viewed pages. Saving new records needs a connection

## Roadmap

- [x] Patient and visit records, allergy alerts, search, dashboard, PDF export
- [x] Two-factor authentication and admin panel
- [x] Multi-clinic support with clinic-level data isolation
- [x] Security hardening and legal pages
- [ ] Live deployment for the pilot
- [ ] Offline data entry with background sync
- [ ] QR-code patient record access
- [ ] Role-based permissions (admin, doctor, nurse)
- [ ] SMS follow-up reminders
- [ ] Native Android app

## About the developer

Built by **Derrick Teddy Wongbay**, a Liberian full-stack developer based in Kénitra, Morocco, studying
IT Engineering (Digital Infrastructure and Full-Stack Development) at Ibn Tofail University.

## Contact

Technical review access, pilot enquiries and collaboration:
**derrickteddywongbay@gmail.com**
[LinkedIn](https://www.linkedin.com/in/derrick-teddy-wongbay-156a7734b)

<p align="center"><i>Built for Liberia 🇱🇷 by a Liberian developer.</i></p>

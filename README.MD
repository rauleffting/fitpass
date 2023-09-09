Fitpass API 
==============

![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white) ![Fastify](https://img.shields.io/badge/fastify-%23000000.svg?style=for-the-badge&logo=fastify&logoColor=white) ![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

![GitHub stars](https://img.shields.io/github/stars/rauleffting/daily-diet-api?style=flat-square) ![GitHub forks](https://img.shields.io/github/forks/rauleffting/daily-diet-api?style=flat-square) ![GitHub watchers](https://img.shields.io/github/watchers/rauleffting/daily-diet-api?style=flat-square) ![GitHub issues](https://img.shields.io/github/issues/rauleffting/daily-diet-api?style=flat-square)

Fitpass is a backend application that provides a RESTful API for gym check-in. It allows users to find gyms nearby, view their info, and check in to use the facilities. 

Features
--------

*   **User can register**: A user can create an account with the application.
*   **User can authenticate**: A user can sign in to the application using their credentials.
*   **User can get logged in user's profile**: A user can view their profile information, such as name, email, and phone number.
*   **User can get the number of check-ins made by logged-in users**: A user can view the number of times they have checked in to a gym.
*   **User can get user's check-in history**: A user can view a list of all the times they have checked in to a gym.
*   **User can search for nearby gyms (up to 10 km)**: A user can search for gyms within a specified distance of their current location.
*   **User can search for gyms by name**: A user can search for gyms by name.
*   **User can check in to a gym**: A user can check in to a gym using a unique code or QR code.
*   **User's check-in can be validated**: A gym can validate a user's check-in.
*   **A gym can be registered**: A gym can create an account with the application.

Technical Features
--------

*   **Continuous Integration**: Automated CI is set up using GitHub Actions. [View Workflow](https://github.com/rauleffting/fitpass/actions)
*   **Commit Linting**: The repository uses Husky and Commitlint to ensure consistent commit messages.
*   **Prisma ORM**: Prisma is used for database migrations and configurations.
*   **JWT Token**: The app provides a secure authentication method using JWT.
*   **Docker compose**: Docker compose is used to run the PostgreSQL database.

Setup
-----

1.  Clone the repository.
2.  Install dependencies using `npm install`.
3.  Set up your environment variables based on the `.env.example` file.
4.  Run docker compose by using `docker compose up -d`.
4.  Start the server using `npm run start:dev`.

Routes
------

#### Users routes

* `POST - /users`

  Create a new user, receiving name, email, and password in the request body.

* `POST - /sessions`

  Users can authenticate.

* `PATCH - /token/refresh`

  Renew access tokens using their refresh tokens.

* `GET - /me`

  Users can access their profile.

#### Gyms routes

* `POST - /gyms/create`

  Create a new gym, receiving title, description, phone, latitude, and longitude.

* `GET - /gyms/search`

  Users can search gyms by using a query.

* `GET - /gyms/nearby`

  Users can search nearby gyms by using users latitude and longitude.

#### Check-ins routes

* `POST - /gyms/:gymId/check-ins`

  Users can create a check-in by using gym ID, and user latitude and longitude.

* `PATCH - /check-ins/:checkInId/validate`

  Gyms can validate users' check-in by using a check-in ID.

* `GET - /check-ins/history`

  Users can access their check-in history.

* `GET - /check-ins/metrics`

  Users can access their total number of check-ins.

Contributing
------------

Contributions are welcome! Please ensure that your commit messages adhere to the Commitlint conventions.

License
-------

This project is open-sourced under the MIT License.

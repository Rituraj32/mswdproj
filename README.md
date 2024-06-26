# 📓 Notion Clone

#### Create and Edit Notes like in Notion

This clone tries to replicate some of the great note-taking features Notion has.

---
---

## Features

- **Slash Commands** (Type `/` to turn the block into different content types)
- **HTML Support** (Use regular HTML tags like `<a>` in text blocks)
- **Image Support** (Upload images by using the `/image` command)
- **Drag And Drop** (Reorder blocks easily by drag and drop)
- **Guest Editing** (Anyone can create public pages and share them via link)
- **User Management** (Create an account to create private pages)
- **Scheduled Jobs** (Delete inactive pages and accounts automatically)

## Tech Stack

The frontend is built with Next.js and fully server-side rendered. On the backend, a REST API handles saving user content and user management.

#### Frontend

Next.js · React.js · SCSS/SASS

#### Backend

Express.js · MongoDB with Mongoose · Nodemailer · JWT (Cookie-based)

## Installation

1. **Clone the project**

   ```sh
    git clone https://github.com/mswdproj/notion-clone.git
    cd notion-clone
   ```
   
2. **Add environment variables**

   Backend: Create an `.env` file in the `backend` directory:

   ```
   FRONTEND_URL="http://localhost:3000"
   DOMAIN="localhost"
   JWT_KEY="yourSecretForTokenGeneration"
   PORT=8080
   MONGO_URI="mongodb+srv://username:password@cluster.gqqwp.gcp.mongodb.net/database?retryWrites=true&w=majority"
   MAIL_HOST="smtp.sendgrid.net"
   MAIL_PORT=465
   MAIL_USER="apiKey"
   MAIL_SENDER="Your Name <your@mail.com>"
   MAIL_PASSWORD="yourSendGridApiKey"
   ```

   Frontend: Create an `.env.local` file in the `frontend` directory:

   ```
   NEXT_PUBLIC_API="http://localhost:8080" // references your Backend API endpoint
   ```

3. **Install and run backend (http://localhost:8080)**

    ```sh
    cd backend
    npm install
    npm start
    ```

4. **Install and run frontend (http://localhost:3000)**

    ```sh
    cd frontend
    npm install
    npm run dev
    ```

## Hosting

You can host the application on almost any provider that supports Node applications and custom domains. I decided to host the frontend on [vercel.com](https://vercel.com) and the backend on [heroku.com](https://heroku.com). But you can host both, frontend and backend, on the same provider if you like to.

### MongoDB Atlas

You have to create a new MongoDB cluster upfront. It will store all of your page and block data. You can create one for free on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).

**Make sure**, you create the following collections:
* pages
* users

**Make sure**, you allow network access to everyone (due to Heroku).

### Backend

If you want to deploy the backend on [heroku.com](https://heroku.com), create a new app in your preferred region on heroku.com.

**Make sure**, you add all production environmental variables for the backend. You can see which variables are needed in the Installation part of this readme.

### Frontend

If you want to deploy the frontend on [vercel.com](https://vercel.com), you can so easily using the Vercel CLI.

With the Vercel CLI, we don't have to make a subtree push, instead we can just switch to the frontend folder and run the `vercel` command to deploy:

```sh
cd frontend
vercel
```

This will lead you through the setup guide for your frontend application. Afterwards the app should be successfully deployed.

**Make sure**, you add the Backend API endpoint as a production environmental variable on Vercel.com.

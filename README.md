# Jenkins Node.js App

## 1. Introduction

This project is a simple Node.js web application built using Express.js. It runs on port `3000` and displays a message in the browser when the root URL is opened. The message refers to Jenkins, a webhook, and the 18 May DevOps batch.

## 2. Architectural Diagram

```text
User / Web Browser
        |
        | HTTP request to /
        v
Node.js Application
        |
        v
Express.js Server (Port 3000)
        |
        v
Response message displayed in browser
```

**Request flow:** The user opens `http://localhost:3000`. Express.js handles the request to `/` and sends a text response to the browser.

## 3. Input

The application receives an HTTP GET request at the root route (`/`).

- **URL:** `http://localhost:3000/`
- **Method:** `GET`
- **Port:** `3000`

No form input or command-line input is required.

## 4. Output

When the user opens the root URL, the browser displays:

```text
Hiii from jenkins, added webhook, we are from 18 May Devops batch
```

## 5. Background – PM2

PM2 is a process manager for Node.js applications. It can keep an application running in the background, restart it if it crashes, and help manage application logs.

To install PM2 globally:

```bash
npm install -g pm2
```

To start the application with PM2 from the project directory:

```bash
pm2 start app.js --name jenkins-node-app
```

To check the application's status:

```bash
pm2 status
```

To view logs:

```bash
pm2 logs jenkins-node-app
```

To restart or stop the application:

```bash
pm2 restart jenkins-node-app
pm2 stop jenkins-node-app
```

The application uses port `3000`, as configured in `app.js`.

## 6. Conclusion

This project demonstrates a basic Node.js and Express.js web server. It handles a GET request at the root route and returns a text message. PM2 can be used to run and manage the application as a background process.

## Prerequisites

- Node.js and npm
- Git (optional, for version control)
- PM2 (optional, for background process management)

## Installation and Execution

Install project dependencies:

```bash
npm install
```

Run normally:

```bash
npm start
```

Or run with PM2:

```bash
pm2 start app.js --name jenkins-node-app
```

Open `http://localhost:3000` in a browser to view the output.

## Project Structure

```text
.
├── app.js
├── package.json
└── README.md
```

## Dependency

- **Express.js** (`^4.18.2`) — used to define the route and send the response.

## Available Script

| Command | Description |
|---|---|
| `npm start` | Runs `node app.js` |

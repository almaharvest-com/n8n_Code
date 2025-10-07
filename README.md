# n8n Webhook Forwarder

This project is a simple Node.js Express server designed to act as a webhook proxy. It receives POST requests on a dynamic endpoint and forwards the request body to a corresponding n8n test webhook, making it easy to integrate services with n8n workflows.

## Key Technologies Used

- **Backend:** Node.js, Express.js
- **HTTP Client:** Axios
- **Middleware:** CORS, body-parser
- **Environment Variables:** dotenv
- **Package Manager:** npm

## Folder Structure Overview

The project follows a simple and organized structure:


n8n_Code/
├── src/

│   └── app.js     # Main application file containing the Express server logic

├── .env.example        # Example environment variables file

├── package.json        # Lists project dependencies and scripts

└── package-lock.json   # Records the exact version of every installed dependency


## Features and Functionalities

- **Webhook Reception:** Sets up a web server to listen for incoming `POST` requests.
- **Dynamic Endpoint:** Uses a dynamic endpoint `POST /webhook-test/:workflowId` to handle requests for different n8n workflows.
- **Data Forwarding:** Forwards the entire JSON body of the incoming request to a specified n8n test webhook URL (`https://n8n.almaharvest.com/webhook-test/:workflowId`).
- **Configurable Port:** The server port can be easily configured using an environment variable.
- **CORS Enabled:** Cross-Origin Resource Sharing is enabled to allow requests from different domains.

## Setup and Installation Steps

Follow these steps to get the project running on your local machine.

**1. Clone the repository:**
bash
git clone https://github.com/almaharvest-com/n8n_Code.git
cd n8n_Code


**2. Install dependencies:**
Make sure you have Node.js and npm installed. Then, run the following command in the project's root directory:
bash
npm install


**3. Configure Environment Variables:**
Create a `.env` file in the root of the project by copying the example file:
bash
cp .env.example .env

Open the `.env` file and set the `PORT` for the server:

# The port the Express server will listen on
PORT=3000


## How to Run and Deploy

### Running Locally

To start the server in a local development environment, run:

bash
npm start


The server will be running at `http://localhost:3000` (or the port you specified in your `.env` file).

**Example Usage:**
To test, you can send a `POST` request to the server using a tool like `curl` or Postman.

bash
curl -X POST http://localhost:3000/webhook-test/your-unique-workflow-id \
-H "Content-Type: application/json" \
-d '{"key1":"value1", "key2":"value2"}'


This will forward the JSON body to `https://n8n.almaharvest.com/webhook-test/your-unique-workflow-id`.

### Deployment

This Node.js application is ready to be deployed on any platform that supports Node.js, such as Heroku, AWS, Vercel, or a traditional VPS.

1.  Ensure your deployment environment has Node.js installed.
2.  Upload the project files.
3.  Install dependencies using `npm install --production`.
4.  Set the `PORT` environment variable in your deployment platform's configuration settings.
5.  Start the application using a process manager like PM2 (`pm2 start src/app.js`) or by running `npm start`.

## Contribution Guidelines

Contributions are welcome! If you'd like to contribute, please follow these steps:

1.  **Fork** the repository.
2.  Create a new **branch** for your feature or bug fix (`git checkout -b feature/my-new-feature`).
3.  Make your changes and **commit** them with clear, descriptive messages.
4.  **Push** your changes to your forked repository (`git push origin feature/my-new-feature`).
5.  Open a **Pull Request** to the `main` branch of the original repository.

## License

This project is licensed under the **ISC License**. See the `package.json` file for more details.

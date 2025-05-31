# Lucia Auth Template

This project is a boilerplate for implementing secure authentication using Lucia, GitHub OAuth, and optional two-factor authentication (2FA) via email. It also features session handling, a simple SQLite database, and modular code organization for easy customization and extension.

## Features

- GitHub OAuth login
- Session management using Lucia
- Two-factor authentication via email (configured for development with Mailtrap)
- SQLite-based user and session storage
- Modular and maintainable project structure

## Project Structure

```
lucia-auth-template/
├── public/               # Static frontend assets
│   ├── index.html
│   └── styles.css
├── index.js             # Main server entry point
├── routes-auth.js               # OAuth and Lucia integration
├──  2fa-email.js              # 2FA email logic
├── database.js                 # SQLite database setup
├── auth-helpers.js         # Helper functions for auth
├── sqlite-adapter.js     # Lucia adapter for SQLite
├── .env                  # Environment variables (excluded from Git)
├── package.json
└── .gitignore
```

## Getting Started

### 1. Create a New Repository

- Click on **“Use this template”** on the GitHub page.
- Set repository details and create your own copy.

### 2. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Configure Mailtrap (for Development Email Testing)

- Create an account at [https://mailtrap.io](https://mailtrap.io).
- In the "Email Testing" section, create a new inbox.
- Copy the SMTP credentials provided by Mailtrap.

### 5. Create the `.env` File

Add the following environment variables to a `.env` file in the root directory:

```
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
SESSION_SECRET=your_session_secret
PORT=3000
NODE_ENV=development
EMAIL_HOST=smtp.mailtrap.io
EMAIL_PORT=2525
EMAIL_USER=your_mailtrap_username
EMAIL_PASSWORD=your_mailtrap_password
```

> Note: This file should not be committed to version control.

### 6. Start the Application

```bash
node server.js
```

Visit `http://localhost:3000` in your browser to test the authentication flow.

## Mailtrap Usage

Mailtrap is configured in this template to handle 2FA via email during development. It provides a secure environment to test email functionality without sending real messages. Emails are captured and displayed in your Mailtrap inbox for review and debugging.

For production use, replace Mailtrap credentials with those of a production-grade email service provider.

## Files Excluded from Version Control

The following files and folders are intentionally ignored via `.gitignore`:

- `.env`, `.env.local`: Contains sensitive configuration values
- `*.db`: SQLite database files (auto-generated)
- `node_modules/`: Installed dependencies
- Log files: `*.log`, `npm-debug.log*`
- System/IDE files: `.DS_Store`, `Thumbs.db`, `.vscode/`, `.idea/`

## Usage

1. Navigate to `http://localhost:3000`
2. Initiate authentication by selecting **Login with GitHub**
3. Enter the 2FA code sent to your Mailtrap inbox
4. After successful login, access the protected dashboard

## Troubleshooting

- **Missing `.env` or variables not recognized**: Ensure the `.env` file exists and values are correct.
- **Database issues**: Verify file system permissions or delete existing `.db` files to reset.
- **Email issues**: Confirm your SMTP credentials in `.env` and ensure the Mailtrap inbox is active.

## License

This project is open-source and available for personal or educational use. For commercial use or redistribution, please review licensing requirements for any third-party dependencies used in the project.

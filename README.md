# SMTP Server

A simple SMTP server implementation built with Node.js using the `smtp-server` package.

## Description

This is a basic SMTP server that can receive emails and log connection details, sender information, recipients, and email data. The server is configured to allow insecure authentication and makes authentication optional for testing purposes.

## Features

- Accept SMTP connections on port 25
- Log connection events and session IDs
- Log sender email addresses
- Log recipient email addresses
- Log email data content
- Allow insecure authentication (for development/testing)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/Ashutosh-88/smtp-server.git
cd smtp-server
```

2. Install dependencies:

```bash
npm install
```

## Usage

Start the SMTP server:

```bash
node index.js
```

The server will start listening on port 25 and display "Server running on 25" when ready.

## Configuration

The server is configured with the following options:

- `allowInsecureAuth: true` - Allows plain text authentication
- `authOptional: true` - Makes authentication optional
- Port: 25 (standard SMTP port)

## Event Handlers

The server implements the following SMTP event handlers:

- **onConnect**: Logs when a client connects
- **onMailFrom**: Logs the sender's email address
- **onRcptTo**: Logs each recipient's email address
- **onData**: Logs the email content as it's received

## Testing

You can test the server using any SMTP client or telnet:

```bash
telnet localhost 25
```

Then follow standard SMTP commands:

```
HELO example.com
MAIL FROM: <sender@example.com>
RCPT TO: <recipient@example.com>
DATA
Subject: Test Email

This is a test email.
.
QUIT
```

## Requirements

- Node.js
- npm

## Dependencies

- `smtp-server`: ^3.14.0

## Dev Dependencies

- `@types/smtp-server`: ^3.5.10

## License

ISC

## Author

Ashutosh-88

## Repository

[GitHub Repository](https://github.com/Ashutosh-88/smtp-server)

## Issues

Report issues at: [GitHub Issues](https://github.com/Ashutosh-88/smtp-server/issues)

## Note

This server is configured for development and testing purposes. For production use, you should implement proper authentication, security measures, and error handling.

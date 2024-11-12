# Chatbot with HTML, CSS, and Gemini API

This project is a simple chatbot built with HTML, CSS, and JavaScript, using Google's Gemini API to generate bot responses. It supports text-based conversations and allows users to upload files as part of their interactions.

## Features

- **Chat Interface**: A clean, interactive chat UI for user-bot conversations.
- **API Integration**: Uses the Gemini API for natural language processing.
- **File Upload**: Allows users to upload and send files to the chatbot.
- **Responsive Design**: User-friendly design, optimized for various screen sizes.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/your-repo-name.git
    cd your-repo-name
    ```

2. Open the project folder and update the `API_KEY` in `script.js`:

    ```javascript
    const API_KEY = "Your API Key";
    ```

3. Open `index.html` in your browser to start using the chatbot.

## Usage

- **Sending Messages**: Type your message in the input box and press Enter or click the "Send" button.
- **File Upload**: Click on the file upload icon to attach a file to the message.
- **Cancel File**: Remove the uploaded file by clicking the cancel button next to the file preview.

## Code Overview

- **HTML**: Basic structure for the chat interface and input elements.
- **CSS**: Styles for the chat interface, including message bubbles, bot avatar, and animations.
- **JavaScript**:
  - `createMessageElement`: Function to create message elements dynamically with custom styles.
  - `generateBotResponse`: Sends a POST request to the Gemini API and processes the response.
  - `handleOutgoingMessage`: Manages outgoing messages from the user, including file attachments.

## Example API Call

```javascript
const requestOptions = {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    contents: [
      {
        parts: [{ text: userData.message }, ...(userData.file.data ? [{ inline_data: userData.file }] : [])]
      }
    ]
  })
};

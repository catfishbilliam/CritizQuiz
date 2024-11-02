# CritiQuiz

CritiQuiz is a web app designed to foster critical thinking in students through conversational quizzes and exams, leveraging OpenAI's ChatGPT API. The app provides a chat-based interface where users can answer questions, receive feedback, and engage in learning exercises.

## Project Structure

This project is organized with clear roles for each file, enabling collaboration and straightforward navigation.

### 1. **server.js**

   **Purpose**: `server.js` is the main backend server file for CritiQuiz. It sets up and configures the Express server, handles routing for user and admin interactions, and connects to the OpenAI API to enable conversational functionality.

   **Main Functions**:
   - **initializeThread()**: Initiates a new session for the user by creating a conversation thread in OpenAI, using the assistant ID and the provided vector store file for file-based question context.
   - **createRunInThread()**: Appends user input to an existing thread, sends it to the assistant, and retrieves the assistant's reply.
   - **retrieveRunResponse()**: Polls OpenAI to retrieve the assistant’s response after user input has been added to a thread.
   - **listRunSteps()**: Lists step-by-step details of assistant responses to facilitate debugging.
   
   **Admin Routes**:
   - **/api/admin/create-thread**: Allows the admin to create a new thread, effectively resetting the assistant for new user sessions.
   - **/api/admin/modify-system-message**: Updates the assistant’s system message, tailoring responses according to instructions.
   - **/api/admin/upload-file**: Enables the admin to upload files (quizzes/tests) for the assistant to utilize during conversations.

### 2. **package.json**

   **Purpose**: Defines project metadata, dependencies, and scripts to streamline app setup and management.

   **Key Fields**:
   - **Dependencies**: Specifies required packages, such as `express`, `dotenv`, and `openai`.
   - **Scripts**: Includes `"start": "node server.js"` for running the server locally or in production.

### 3. **style.css**

   **Purpose**: Provides CSS styling for all app pages, including responsive adjustments for mobile screens.

   **Main Sections**:
   - **General Layout**: Styles `.container`, `.button-row`, and `.role-button` to create a cohesive, centered layout.
   - **Responsive Design**: Media queries adjust layouts and font sizes for optimal mobile experience.
   - **User and Admin Themes**: Different color schemes for role buttons and login elements based on user type selection.

### 4. **index.html**

   **Purpose**: The landing page where users choose between "User" or "Admin" roles. Displays the login form dynamically based on the selected role.

   **Main Components**:
   - **Role Selection Buttons**: Two buttons for "User" and "Admin" that reveal the login form upon selection.
   - **Login Form**: Appears after role selection, with inputs for username and password, dynamically adjusting to user or admin login.

### 5. **admin.html**

   **Purpose**: The admin portal page where admins can create new sessions, update system instructions, and upload new files for assessments.

   **Key Sections**:
   - **Create New Thread**: A button that resets the assistant’s thread, allowing new user sessions to begin fresh.
   - **Modify System Message**: Text area where admins can alter the assistant's instructions, shaping how responses are generated.
   - **File Upload Section**: Input and button for uploading new quizzes or tests, updating the assistant’s file context for future interactions.

### 6. **user.html**

   **Purpose**: The main chat interface for users, where quizzes and assessments are conducted in a conversational format.

   **Key Features**:
   - **Chat Display Area**: Displays a threaded conversation view between the user and the assistant.
   - **Input Area**: Text input where users can type responses to questions, submit answers, and engage with the assistant.
   - **Send Button**: Triggers submission of user input and appends both the user’s message and the assistant’s response to the chat display.

## Getting Started

### Prerequisites
- **Node.js**: Ensure you have Node.js installed.
- **Azure Web App** (for deployment): Follow Azure setup to deploy your app.
- **OpenAI API Key**: Place in a `.env` file for security.

### Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/CritiQuiz.git
  
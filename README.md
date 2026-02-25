**"The Guardian" - QueenB X AppsFlyer - BeSafe Hackathon 2026**

"The Guardian" - Digital Emotional Notebook for Kids
"The Guardian" is a full-stack application developed for the QueenB X AppsFlyer 2026 Hackathon. It is designed to provide children with a safe space to document their daily emotions while ensuring parental oversight and verification.

**Project Goals**

Parent-Child Dual Registration: Child accounts are linked to a parent's email, requiring a 6-digit verification code sent to the parent to activate the account.

Digital Notebook: A structured journal where children answer guided questions (e.g., "How did you feel today?") and engage in free-text writing.

AI Agent Integration: Free-text entries are analyzed by an AI agent to help interpret the child's emotional state and provide context.

Safety & Verification: Ensuring only verified users can access the journal features.

**Tech Stack**

Frontend: React (Vite)

Backend: Node.js & Express

Database: MongoDB (via Mongoose)

Authentication: JWT (JSON Web Tokens) & Bcryptjs for password hashing

Services: Nodemailer for parental email verification

**Key Features & Workflow**

Registration: The child signs up with their email and their parent's email. A verification code is automatically generated and emailed to the parent.

Verification: The child enters the code provided by the parent. The account status is updated to isVerified: true.

Digital Journaling: Once logged in, children can access their JournalPage.

AI Analysis: The textAnalysisController processes free-text entries to determine moods or flags.

Personalization: Children can choose and update their unique avatars.

**Project Structure**
**Client Directory (client/)**
Contains the React (Vite) frontend application designed for the digital notebook experience.

package.json: Lists the client-side dependencies (like react-router-dom) and scripts for managing the React application.

.env: Stores environment variables, specifically the VITE_SERVER_API_URL used to communicate with the Node.js backend.

index.html: The main HTML entry point where the React application is mounted.

public/: Contains static assets like the site favicon that are not processed by the build pipeline.

src/: Contains the source code for the BeSafe frontend.

  api/: Centralized API configurations (e.g., authApi.js) for handling network requests.

  assets/: Contains processed images, including the child avatars (bunny.png, cat.png, dog.png, lion.png) used in the Profile Page.

  components/: Reusable UI modules, including specialized folders for Journal inputs and Stickers, as well as common components like LoginForm.jsx and RegisterForm.jsx.

  hooks/: Custom React hooks for encapsulating complex logic, such as useLogin.js, useRegister.js, and useVerify.js for the child-parent flow.

  pages/: Individual view components representing application routes:

    RegisterPage: The main entry point for new users.

    LoginPage: Secure portal for verified users.

    VerificationPage: Where children enter the 6-digit code sent to their parents.

    JournalPage: The digital notebook interface for logging daily emotions and free text.

    ProfilePage: Where users can view their status and update their avatars.

  services/: Contains api.js (Axios configuration) and journalApi.js for handling notebook-specific business logic.

  styles/: Contains global and component-specific CSS modules (e.g., App.module.css) to maintain a kid-friendly UI.

  utils/: Utility functions, notably validation.js for checking child/parent email formats and password strength.

  App.jsx: The main component setting up the application layout, navigation, and Routes.

  index.jsx: The application entry point that wraps App in BrowserRouter and StrictMode.

**Server Directory (server/)**
package.json: Lists server-side dependencies, including bcryptjs for security and nodemailer for parental verification emails.
server.js: The main entry point that initializes the Express server, establishes the MongoDB connection, and mounts all application routes.
controllers/: Contains the core business logic for handling client requests:
  authController.js: Manages the multi-step registration flow (child signup/parent email), verification code logic, and secure user login.
  journalController.js: Handles the creation, retrieval, and organization of a child’s digital journal entries.
  textAnalysisController.js: Coordinates with the AI agent to analyze free-text entries for emotional context.
middleware/: Contains functions that run during the request-response cycle, such as errorHandler.js for uniform error reporting and middleware.js for JWT authentication checks.
models/: Defines the data structure using Mongoose schemas:
  User.js: Stores account details, including child/parent email links and verification status.
  journal.js: Defines the structure for emotional logs, mood selections, and AI-generated feedback.
routes/: Maps API endpoints (e.g., /api/auth) to their specific controller functions.
services/: Houses external utility logic:
  emailService.js: Dedicated logic for sending 6-digit verification codes to parents.
  journalLogic.js: Backend helper functions for processing notebook data.
utils/: General helper files, such as emailTemplates.js for consistent, child-friendly email communication.

# "The Guardian" - QueenB X AppsFlyer - BeSafe Hackathon 2026

"The Guardian" - Digital Emotional Notebook for Kids
"The Guardian" is a full-stack application developed for the QueenB X AppsFlyer 2026 Hackathon. It is designed to provide children with a safe space to document their daily emotions while ensuring parental oversight and verification.

Project Goals

Parent-Child Dual Registration: Child accounts are linked to a parent's email, requiring a 6-digit verification code sent to the parent to activate the account.

Digital Notebook: A structured journal where children answer guided questions (e.g., "How did you feel today?") and engage in free-text writing.

AI Agent Integration: Free-text entries are analyzed by an AI agent to help interpret the child's emotional state and provide context.

Safety & Verification: Ensuring only verified users can access the journal features.

Tech Stack

Frontend: React (Vite)

Backend: Node.js & Express

Database: MongoDB (via Mongoose)

Authentication: JWT (JSON Web Tokens) & Bcryptjs for password hashing

Services: Nodemailer for parental email verification

Key Features & Workflow

Registration: The child signs up with their email and their parent's email. A verification code is automatically generated and emailed to the parent.

Verification: The child enters the code provided by the parent. The account status is updated to isVerified: true.

Digital Journaling: Once logged in, children can access their JournalPage.

AI Analysis: The textAnalysisController processes free-text entries to determine moods or flags.

Personalization: Children can choose and update their unique avatars.

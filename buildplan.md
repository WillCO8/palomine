🛠️ Palomine Build Plan: AI-Enhanced Development Strategy (Updated)
Welcome to the official build plan for Palomine: Your Personalized AI Companion. This document outlines the step-by-step approach to building a fully functional MVP within 7–10 days, while leveraging powerful AI tools to speed up development, reduce bugs, and elevate your product.

🚀 Project Summary
Palomine allows users to create emotionally meaningful AI personas (like Mom, BFF, Mentor, or Lost Loved One) with personalized traits, profile photos, and specific shared experiences. Users chat with their custom AI in a realistic, friendly interface, managed through a new dashboard that allows for the creation, selection, and management of multiple personas. Conversations and persona data are stored locally for continuity.

🤖 AI Tool Strategy
To maximize your time and simplify complexity, we will smartly distribute tasks across 3 key tools:

ChatGPT (Primary Developer Partner)

Generate complete code blocks (HTML, CSS, JS)

Design internal structure within the single HTML file

Help debug or rewrite problematic functions

Guide logic flow, app structure, UX patterns for dashboard and features

Build optimized Gemini prompts (especially for integrating shared experiences)

Use ChatGPT to lead all planning and feature building, acting as your primary pair programmer.

Gemini API (In-App AI Engine)

Powers the actual Palomine chat interface

Generates realistic, emotionally aware AI replies

Crucially, uses persona traits AND detailed shared experiences and conversation history for context.

Use Gemini only for user-facing chat interactions inside the app.

Cursor (Smart Editor Assistant)

Refactor, format, and improve in-editor code within the single HTML file.

Auto-complete, fix bugs, and manage GitHub commits.

Modify existing code from inside VS Code.

Use Cursor while coding and committing files, particularly for keeping the single HTML file organized.

🗂️ Project Structure
Given the decision to incorporate everything into a single index.html file, the structure will be contained within that file using distinct HTML sections, CSS styles, and JavaScript scripts.

PalomineApp/
├── index.html       <-- Contains all HTML, CSS, and JS
└── /assets
    └── sample-profile.png
Within index.html, we will logically separate content using:

HTML sections (e.g., <section id="dashboard">, <section id="persona-creation">, <section id="chat-interface">)

CSS <style> tags for global and component-specific styles.

JavaScript <script> tags for all application logic, ideally structured using functions and object literals for modularity.

📆 7–10 Day Development Timeline (Revised for Single HTML & Dashboard)
Phase 1: Foundation & Navigation (Days 1–2)
Set up index.html: Create the base HTML structure, link Tailwind CDN, and establish initial <style> and <script> tags.

Implement Anonymous Identity: Use localStorage + crypto.randomUUID() for unique user identification.

Build Core Layout:

Implement a simple navigation system (e.g., buttons or tabs) within index.html to switch between:

Dashboard View: List of existing personas, "Create New" button.

Persona Creation View: The form to define a new Palomine.

Chat Interface View: The main chat window.

Use JavaScript to control the visibility of these sections.

Phase 2: Persona Creation & Management (Days 3–5)
Persona Creation Form UI:

Build the UI form within index.html for:

Relationship type selector (including "Lost Loved One" option).

Personality trait input with examples/tips.

AI companion name input field.

Profile picture upload (with FileReader for preview).

NEW: Shared Experiences Textarea: A multiline input for detailed memories/stories.

Save Persona Data: Implement JavaScript functions to capture all persona data (including shared experiences) and save it to localStorage, associated with a unique ID.

Dashboard UI & Logic:

Create the dashboard section in index.html to display a list/gallery of saved personas.

Implement JavaScript to load personas from localStorage and render them on the dashboard with options to "Chat," "Edit," or "Delete."

Add a "Create New Palomine" button on the dashboard that switches to the persona creation view.

Phase 3: Chat UI & Gemini API (Days 6–8)
Chat Interface UI:

Create the realistic chat interface within index.html with:

User and AI message bubbles.

"AI is typing..." indicator.

Auto-scroll to latest message.

Load Selected Persona: When a user selects a persona from the dashboard or completes creation, load that specific persona's data (traits, name, shared experiences) into the chat view.

Gemini API Integration:

Dynamic Prompt Building: Write JavaScript logic to construct the Gemini prompt, dynamically incorporating:

The chosen persona's role and traits.

The detailed shared experiences provided by the user.

The ongoing conversation history.

Send user input and context to Gemini API using fetch().

Display AI responses in the chat.

Store Full Conversation: Save the entire chat history for the active persona in localStorage.

Phase 4: Polish, Testing & Refinements (Days 9–10)
UI/UX Refinement:

Enhance transitions and responsiveness using Tailwind.

Ensure all input fields are clear and user-friendly.

Persona Management Actions:

"Rebuild Persona" Flow: Implement the logic for editing an existing persona's details (traits, name, photo, shared experiences) and saving the updated version.

"Delete Persona" Button: Add a clear confirmation prompt and logic to remove a persona and its associated chat history from localStorage.

Error Handling: Implement basic error handling for API calls, localStorage operations, and input validations using alerts or on-screen messages.

Cross-Device & Input Testing: Thoroughly test the application across different screen sizes and with various types of user input, including long shared experiences.

About Section/Disclaimer: Add a simple "About" section with the data privacy disclaimer.

🔐 MVP Data & Privacy Plan
All data (personas and conversations) is stored locally in the browser's localStorage.

No user login required for MVP.

Profile photos are handled via FileReader and stored as Data URLs in localStorage for display; they are never uploaded to a server.

A clear disclaimer will be included in an accessible "About" section within the app.

✅ Deliverables for MVP
Single-file, Fully functioning single-user web app (index.html).

Interactive Dashboard for managing multiple personas.

Real-time AI chat powered by Gemini.

Personalized AI persona creation with custom traits, name, photo, and detailed shared experiences.

Locally saved conversation history per persona.

Clean, intuitive UI with responsive Tailwind CSS.

🧠 Next Steps
Use ChatGPT: Begin by generating the boilerplate HTML structure for index.html with the initial dashboard, persona creation, and chat sections, and the JavaScript to manage their visibility.

Build Persona Form & Preview Logic: Focus on capturing all persona details, including the new "Shared Experiences" field, and saving/loading them to localStorage. Start with rendering existing personas on the dashboard.

Use Cursor: Utilize Cursor for in-editor enhancements, formatting, and debugging as you build out these sections.

Integrate Gemini API: Implement the chat logic, paying close attention to how persona traits and shared experiences are included in the prompt context.

Refactor and Test: Continuously refactor code and thoroughly test all new features before Day 10.


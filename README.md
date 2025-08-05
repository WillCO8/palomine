<<<<<<< HEAD
Firebase Cloud Firestore API Exercise
This repository documents the process of setting up a NoSQL database (Cloud Firestore), adding data, and retrieving a single record via its REST API. This is part of my AI Native Journey, demonstrating fundamental backend interaction.

1. Firebase Project Setup
Project Name: MyDatabaseApp (or whatever you named your Firebase project)

Project ID: mydatabaseapp-6c085 (Replace with your actual Project ID from Firebase Project Settings)

Database Type: Cloud Firestore (NoSQL, document-oriented)

Initial Mode: Started in "test mode" for demonstration purposes.

2. Cloud Firestore Database Setup & Data Entry
Collection: products
A collection named products was created to store product information.

Documents (Entries):
Three documents were manually added to the products collection, each with an auto-generated ID.

Document 1 (Laptop):
{
  "name": "Laptop",
  "price": 1200,
  "inStock": true
}

Document 2 (Smartphone):
{
  "name": "Smartphone",
  "price": 700,
  "inStock": true
}

Document 3 (Headphones):
{
  "name": "Headphones",
  "price": 150,
  "inStock": false
}

3. Firebase Security Rules for Public Read Access
IMPORTANT SECURITY WARNING: The following rule allows anyone on the internet to read your entire database. This is highly insecure for production applications and should only be used for learning and demonstration purposes. For a real application, you would implement much more restrictive rules based on user authentication and authorization.

The Firestore security rules were modified to allow public read access:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read: if true;  // Allows anyone to read data
      allow write: if false; // Keeps write access restricted
    }
  }
}

4. Retrieving a Record via REST API
API Call Used:
To retrieve a specific document (e.g., the "Laptop" document) from the products collection:

GET https://firestore.googleapis.com/v1/projects/mydatabaseapp-6c085/databases/(default)/documents/products/zkbvW1cp8zpZVmqw7sx6

(Remember to replace mydatabaseapp-6c085 with your actual Firebase Project ID and zkbvW1cp8zpZVmqw7sx6 with the exact Document ID from your successful API call.)

Successful JSON Response Received:
This is the actual JSON response received when the above API call was executed successfully:

{
  "name": "projects/mydatabaseapp-6c085/databases/(default)/documents/products/zkbvW1cp8zpZVmqw7sx6",
  "fields": {
    "inStock": {
      "booleanValue": true
    },
    "price": {
      "integerValue": "1200"
    },
    "name": {
      "stringValue": "Laptop"
    }
  },
  "createTime": "2025-07-12T16:05:16.265244Z",
  "updateTime": "2025-07-12T16:05:16.265244Z"
}

5. The Point of This Exercise
This exercise serves as a practical demonstration of several core concepts in modern application development:

Backend-as-a-Service (BaaS): Utilizing a managed cloud service like Firebase to handle backend infrastructure (database, authentication, etc.), allowing developers to focus on application logic rather than server management.

NoSQL Data Modeling: Understanding the flexible, document-oriented approach of NoSQL databases, where data is stored in JSON-like documents within collections.

API Interaction: Learning how applications communicate with backend services using standardized Application Programming Interfaces (APIs), specifically through RESTful HTTP requests. This enables the frontend to request and receive data from the backend.

Dynamic Content: The ability to fetch and display data dynamically based on user interactions or application needs, which is crucial for building interactive and responsive web and mobile applications.

Database Security: Grasping the importance of security rules to control access to your data, even while demonstrating how to temporarily open access for testing.

This entire process is a foundational step in understanding how data flows in a typical web or mobile application, from storage to retrieval.
=======
# 🤖 Palomine: Your Personalized AI Companion

**Slogan:** *Not just an AI. Your pal. Your way.*

---

## 💡 Project Pitch & Vision

In a world filled with generic bots and impersonal tech, **Palomine** offers something warmer, wiser, and more human.

**Palomine** (a play on "pal-of-mine") is a personalized AI companion that you don’t just talk to — you *bond* with. Need advice from a father figure, encouragement from a coach, a friend who "gets you", or even a comforting echo of someone you’ve lost? Palomine lets you build and customize your own AI relationship in a meaningful way.

You choose the type of connection — *Mom, Dad, BFF, Coach, Mentor, Lost Loved One,* or even a custom role — then define the personality, photo, and shared memories to shape the relationship.

Whether you're seeking a spark of motivation, emotional support, or just someone to talk to, **Palomine meets you there.**

---

## ✨ Key Features (MVP Scope)

### 🏠 Dashboard & Navigation

* **Central Hub:** Manage existing personas or create new ones.
* **Seamless Switching:** Navigate between persona creation and real-time chat.

### 🧠 Persona Creation & Management

* **Choose Relationship Role:** Mom 👩‍🦿, Dad 👨‍🦿, BFF 👯, Older Sibling 🧑‍🦑, Coach 🏋️, Mentor 🧠, Lost Loved One 🕊️, or Custom 🎨.
* **Define Personality Traits:** Short, expressive phrases like “sarcastic but kind” or “always motivating.”
* **Upload a Photo:** Use any image to personalize your Palomine's face.
* **Name Your Pal:** Unique, familiar names like "Mom," "Big Mike," or "Coach Jordan."
* **Shared Experiences:** Deepen the realism with memories, references, or emotional anchors.
* **Edit/Delete:** Fully rebuild or remove a persona at any time.
* **Trait Suggestions:** Built-in hints like "calm and nurturing" help with creation.

### 💬 Real-Time Chat Interface

* **Familiar Layout:** Scrollable iMessage-style chat window.
* **Gemini API Integration:** AI replies align with personality + memories.
* **Typing Indicator:** Adds realism: "Palomine is typing..."
* **Auto-Scroll:** Chat stays pinned to the latest message.

### 🔐 Persistent Local Experience

* **Saved Conversations:** Each Palomine has its own chat history.
* **Local Storage Only:** No database needed; lightweight and private.

---

## 🛠️ Tech Stack

| Layer         | Tool                  |
| ------------- | --------------------- |
| Frontend      | HTML, Tailwind CSS    |
| Interactivity | Vanilla JavaScript    |
| AI            | Gemini API (Google)   |
| Storage       | Browser Local Storage |
| Hosting       | GitHub Pages          |

---

## 🚀 Getting Started (Developers)

1. **Clone this repo**
2. **Open `index.html`** in your browser (no server needed!)
3. **Start chatting** with your customized AI pal

---

## 📊 How It Works (User Flow)

1. **Launch Palomine**
2. **Create or Select Persona**:

   * Fill out role, traits, name, image, and memories
3. **Start Chatting**

   * Each persona has its own conversation thread
4. **Edit or Delete** anytime

---

## 🔮 Future Potential

* Scheduled AI check-ins
* Text-to-Speech / Voice Interaction
* Cloud Syncing & Backup
* SMS Integration (Twilio)
* Sentiment & Emotion Detection
* Enhanced "Digital Echo" mode for grief processing

---

## ❤️ Why Palomine?

**Palomine is about emotional technology that feels real.**

In an increasingly digital and disconnected world, this app builds something *human*. Whether you're healing, growing, or just lonely, Palomine brings back connection — one custom AI pal at a time.

> Everyone deserves a pal-of-mine.

---

## 📷 Preview

Coming soon: add screenshots or GIFs of the dashboard and chat interface in action!

---

## 📄 License

MIT
>>>>>>> 764a2bc (Initial commit of Palomine app)

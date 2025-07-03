
# 🧠 Conversational AI Agent — Meeting Booking Assistant

This project is a **Conversational AI Booking Agent** built with **LangGraph**, **Google Calendar API**, and **Streamlit**. Users can chat naturally to **book meetings, check availability**, and engage in small talk.

It supports both **signed-in users** (via Firebase) and **guest users**. All meeting bookings are integrated in real-time using Google Calendar.

---

## ✨ Features

- ✅ Book meetings using natural language (e.g., "Book a meeting next Friday at 2 PM")
- ✅ Check calendar availability (e.g., "What slots are available this Tuesday?")
- ✅ Built-in fallback replies for general conversation
- ✅ Save chat history for signed-in users
- ✅ Guest mode support
- ✅ Google Calendar real-time integration
- ✅ Light/Dark theme set to **Dark mode by default**
- ✅ Toast notifications for login, logout, signup, and errors
- ✅ Loading indicators during API response time

---

### 🧰 Tech Stack

| Layer                         | Technology Used                                      |
|------------------------------|-------------------------------------------------------|
| **Frontend**                 | Streamlit – Chat interface                            |
| **Backend**                  | FastAPI – API server for agent handling               |
| **Authentication & Database**| Firebase (via Pyrebase) – Auth + Realtime Database   |
| **Conversational Agent**     | LangGraph (LangChain) + OpenAI GPT-3.5 Turbo         |
| **Meeting Management**       | Google Calendar API – Check & book events            |
| **Natural Language Parsing** | `dateparser` – Understand natural time expressions    |

---

## 📁 Project Structure

```
conversational_ai_agent/
├── backend/
│   ├── main.py                # FastAPI app entry point
│   ├── calendar_utils.py      # Google Calendar API integration
│   ├── agent.py               # LangGraph AI logic
│   ├── config.py              # Google scopes and settings
│   └── models.py              # Pydantic models for chat
│
├── frontend/
│   ├── app.py                 # Streamlit UI
│   └── firebase_config.py     # Firebase API keys
│
├── credentials/
│   └── credentials.json       # Google OAuth client secrets
│
├── .env                       # Environment variables (API keys)
├── token.pickle               # Saved Google token (first-time OAuth)
├── requirements.txt           # All dependencies
└── README.md                  # Project instructions
```

---

## 🔐 Authentication Options

- **Signup/Login** using Firebase email & password auth
- **Guest Mode** to try the assistant without registration

> ⚠️ **Note:** If you continue as a guest, **your chat history will not be saved** after refresh or logout.

---

## 🧪 Example Commands You Can Try

- "Book a meeting tomorrow at 3 PM"
- "Check my availability on Wednesday"
- "Do I have any free time next Friday afternoon?"
- "Book a slot next week between 2 and 5 PM"
- "Hey" / "Thanks" / "How are you?" → receives friendly fallback replies

---

## 🛠 Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/your-username/conversational_ai_agent.git
cd conversational_ai_agent
```

### 2. Set up your environment
```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

### 3. Create a `.env` file
```env
GOOGLE_CALENDAR_ID=your_calendar_id_here
OPENAI_API_KEY=your_openai_api_key
```

Place your Google OAuth credentials in `credentials/credentials.json`.

---

## ▶️ Running the Application

### Step 1: Start the backend
```bash
uvicorn backend.main:app --reload
```

### Step 2: Start the frontend
```bash
streamlit run frontend/app.py
```

---

## 🏁 Final Notes

- The booking assistant is designed to be intuitive and user-friendly.
- Built-in fallback logic ensures it responds gracefully even without OpenAI API availability.
- Firebase login enables persistent user-specific chat history.
- Guest users can still book meetings, but their chat history will be lost upon reload.

---

## 👨‍💻 Developed by

**Pavan Kumar K** 

**Karunakar K**
 

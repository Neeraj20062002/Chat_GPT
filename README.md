# 🤖 Assistant-UI Chat App

A modern conversational web app built using **Next.js 15** and **Assistant-UI**, providing a sleek, developer-friendly chat interface powered by AI.

> Adapted from the official [Assistant-UI Getting Started guide](https://www.assistant-ui.com/docs/getting-started).

---

## 🚀 Features

- ⚡ Built with **Next.js 15 + Turbopack**
- 💬 Interactive chat interface using **Assistant-UI**
- 🧱 Modular and scalable project structure
- 🔄 Backend API route for handling AI responses
- 🧰 Ready for local development or Vercel deployment

---

## 🛠️ Prerequisites

Make sure you have:

- [Node.js 18+](https://nodejs.org/)
- npm or pnpm

---

## ⚙️ Setup

Before running the project, create a `.env.local` file in the root directory  
and add your required API key(s) or environment variables.

**Example:**
```bash
# .env.local
OPENAI_API_KEY=your_openai_api_key_here
🧩 Project Structure
ruby
Copy code
assistant-ui-chat-app/
│
├── app/                     # Next.js 15 app directory
│   ├── api/assistant/route.ts   # API route handling chat requests
│   └── page.tsx             # Main chat interface
│
├── components/              # Reusable UI components
│   └── ChatUI.tsx           # Core Assistant-UI chat component
│
├── public/                  # Static assets
├── styles/                  # Global CSS / Tailwind styles
├── .env.local               # Environment variables (not committed)
├── package.json             # Dependencies & scripts
├── next.config.js           # Next.js configuration
└── README.md                # Documentation
💻 Installation & Run
1️⃣ Clone the repository
bash
Copy code
git clone https://github.com/Neeraj20062002/assistant-ui-chat-app.git
cd assistant-ui-chat-app
2️⃣ Install dependencies
bash
Copy code
npm install
# or
pnpm install
3️⃣ Start the development server
bash
Copy code
npm run dev
# or
pnpm dev
4️⃣ Visit
Open http://localhost:3000 in your browser to start chatting 💬

🧠 How It Works
The Assistant-UI component provides a dynamic frontend chat interface.

Each message is sent to the /api/assistant backend route.

The backend route connects to an AI model (like OpenAI API).

Responses are streamed back to the frontend in real-time.

🧾 Example API Route (TypeScript)
ts
Copy code
// app/api/assistant/route.ts
import { NextResponse } from "next/server";

export async function POST(req: Request) {
  const { messages } = await req.json();

  // Example AI integration (pseudo-code)
  const reply = await fetch("https://api.openai.com/v1/chat/completions", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: `Bearer ${process.env.OPENAI_API_KEY}`,
    },
    body: JSON.stringify({
      model: "gpt-4o-mini",
      messages,
    }),
  }).then((res) => res.json());

  return NextResponse.json(reply);
}
🌐 Deployment
You can easily deploy this app to Vercel:

bash
Copy code
vercel deploy
Or manually build & export:

bash
Copy code
npm run build
npm start
📊 Future Enhancements
🔒 Authentication (NextAuth / Clerk)

🧩 Plugin-based conversation extensions

🪄 Theme customization (light/dark mode)

💾 Persistent chat history using Supabase or Firebase

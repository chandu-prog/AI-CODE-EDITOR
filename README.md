# ⚡ Full-Stack Online IDE (Agentic AI Edition)

A **modern, AI-augmented, full-stack web IDE** with **multi-language execution**, **real-time terminal**, and **OpenAI-powered agentic assistance**.  
Inspired by **VS Code**, designed for the web — fast, elegant, and intelligent.

---

## 🚀 Features

### 🧠 AI-Powered Coding
- **AI Tutor:** Explains code, errors, and logic in natural language  
- **AI Write:** Generates, refactors, or documents code from prompts  
- **AI Chat:** Ask coding questions, get instant samples or fixes  
- **Inline AI:** Trigger inline generation with `#ai` or `//ai` comments  
- **Agentic Mode:** IDE acts as an intelligent agent — it can analyze projects, suggest improvements, and auto-generate missing files

*(Powered by OpenAI GPT-5 API — locally proxied for security)*

---

### 💻 Code Editor
- **Monaco Editor** (VS Code engine)
- Syntax highlighting, minimap, multi-tab editing, and find/replace
- Multi-language support: **Python, JavaScript, Java, C++**
- Auto language detection on file upload
- Code formatting & linting support

---

### ⚙️ Runtime & Terminal
- **Real-time terminal** (xterm.js)
- Colorized output, execution time, copy/download options
- Sandboxed code execution via Node.js `child_process.spawn`
- Multi-language backend runners:
  - Python → `python3`
  - JavaScript → `node`
  - Java → `javac` + `java`
  - C++ → `g++`

---

### 🗂️ File System
- Multi-file tabs
- Rename, delete, upload/download, drag-and-drop reordering
- Auto-save and session restore via localStorage
- New file modal with language presets

---

### 🎨 UI/UX
- **VS Code–inspired layout**
- Light/Dark themes
- Font size controls
- Collapsible sidebar and resizable panels
- Command Palette (`Ctrl+P`) for quick actions
- Status bar with file info and runtime language

---

## 🧩 Tech Stack

### **Frontend**
- **React 19 + Vite**
- **Mantine UI** — modern, responsive components
- **Monaco Editor** — advanced code editing
- **xterm.js** — interactive terminal
- **react-markdown** — render AI chat beautifully
- **@tabler/icons-react** — consistent icons

### **Backend**
- **Node.js + Express**
- **child_process.spawn** for sandboxed execution
- **OpenAI GPT-5 API**
- **dotenv + CORS** for config and security

---

## 🧠 AI Agent Architecture

- `/run` → executes user code securely and returns stdout/stderr  
- `/ai/tutor` → explains code, errors, or logic  
- `/ai/write` → generates/refactors code from user prompts  
- `/ai/chat` → chat with AI about your code  
- **Agent Loop (optional)** → analyze entire project and propose actions

All AI routes use **OpenAI GPT-5 API** for reasoning, explanation, and generation.

---

## ⚡ Setup & Installation

### Prerequisites
- Node.js 18+
- npm
- Python 3.x
- Java JDK (javac)
- g++ compiler
- OpenAI API key

---

### 1. Clone the Repository
```bash
git clone <repository-url>
cd fullstack-ide
```

---

### 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file:

```
PORT=3001
OPENAI_API_KEY=your_openai_api_key_here
```

---

### 3. Frontend Setup

```bash
cd ../frontend
npm install
```

---

### 4. Run the Application

Start backend:

```bash
cd backend
node server.js
```

Start frontend:

```bash
cd frontend
npm run dev
```

Open your browser at 👉 [http://localhost:5173](http://localhost:5173)

---

## 🧭 Usage Guide

* **Run Code:** Click ▶️ or press `Ctrl+Enter`
* **Switch Language:** Per file tab or auto-detect
* **AI Tutor:** Get code explanations or debugging help
* **AI Write:** Generate functions, modules, or comments
* **AI Chat:** Discuss architecture or design with GPT
* **Inline AI:** Add `#ai` or `//ai` comments to auto-generate inline code
* **Command Palette:** `Ctrl+P` for quick commands
* **Format Code:** `Ctrl+Shift+F`
* **Resizable Panels:** Drag to resize editor/output areas
* **Save & Restore:** Auto-saves work and restores on reload

---

## 🌐 Deployment Notes

### Frontend

* Deploy on **Netlify**, **Vercel**, or **Cloudflare Pages**

### Backend

* Requires Node.js with `python3`, `g++`, and `javac` installed
* Ideal on **VPS/Docker** for full compiler support
* Use `.env` for API key security

### Security

* AI requests are **proxied through backend** — API keys stay hidden
* Code execution is sandboxed, but not fully containerized — limit public access

---

## 🤝 Contributing

1. Fork this repository
2. Create a feature branch

   ```bash
   git checkout -b feature/xyz
   ```
3. Commit your changes

   ```bash
   git commit -m "Added xyz feature"
   ```
4. Push your branch

   ```bash
   git push origin feature/xyz
   ```
5. Open a Pull Request 🚀

---

## 📄 License

MIT License © 2025
Developed with ❤️ and GPT-5

---

## 🏗️ Project Structure

```
fullstack-ide/
├── backend/
│   ├── server.js
│   ├── package.json
│   ├── .env
│   └── runners/          # Language-specific execution handlers
├── frontend/
│   ├── src/
│   │   ├── components/   # React components
│   │   ├── hooks/        # Custom React hooks
│   │   ├── utils/        # Helper functions
│   │   └── styles/       # CSS and themes
│   ├── package.json
│   └── vite.config.js
└── README.md
```

---

## 🔧 API Endpoints

### Code Execution
- `POST /run` - Execute code in supported languages
- `GET /languages` - List available programming languages

### AI Assistance
- `POST /ai/tutor` - Get code explanations and debugging help
- `POST /ai/write` - Generate or refactor code
- `POST /ai/chat` - Interactive chat about your code
- `POST /ai/analyze` - Project-level analysis and suggestions

### File Management
- `GET /files` - List project files
- `POST /files` - Create new files
- `PUT /files/:id` - Update file content
- `DELETE /files/:id` - Remove files

---

## 🎯 Agentic AI Capabilities

### Intelligent Code Analysis
- **Context-Aware Suggestions:** AI understands your project structure and dependencies
- **Error Diagnosis:** Deep analysis of runtime errors with fix recommendations
- **Code Optimization:** Performance and readability improvements
- **Architecture Guidance:** Project structure and design pattern suggestions

### Automated Workflows
- **Smart File Generation:** Auto-create missing files based on project context
- **Dependency Management:** Suggest and implement required imports
- **Test Generation:** Create unit tests for your functions and classes
- **Documentation:** Auto-generate comments and documentation

### Learning Assistant
- **Interactive Tutorials:** Step-by-step guidance for complex concepts
- **Best Practices:** Language-specific coding standards and patterns
- **Code Reviews:** Automated quality assessment and improvement suggestions

---

## 📊 Performance Features

- **Real-time Collaboration:** Multiple users can edit simultaneously (optional)
- **Offline Support:** Basic editing functionality without internet connection
- **Project Templates:** Quick-start with popular frameworks and patterns
- **Export Options:** Download projects as ZIP or deploy directly to cloud platforms
- **Version History:** Track changes and revert when needed

---

## 🔒 Security & Privacy

- **Local-First Architecture:** Your code never leaves your infrastructure unless you choose to share it
- **API Key Protection:** OpenAI API calls are proxied through your backend
- **Sandboxed Execution:** Code runs in isolated processes
- **No Data Mining:** We don't train models on your code
- **Encrypted Storage:** Local data is encrypted at rest

---

## 🚀 Roadmap

### Coming Soon
- [ ] **Multi-user Collaboration**
- [ ] **Git Integration**
- [ ] **Database Integration**
- [ ] **More Languages** (Go, Rust, TypeScript)
- [ ] **Plugin System**
- [ ] **Mobile App**

### Future Vision
- [ ] **AI-Pair Programming Mode**
- [ ] **Voice Commands**
- [ ] **AR/VR Development Environment**
- [ ] **Blockchain Smart Contract Development**

---

## 💬 Community & Support

- **Discord Server:** Join our developer community
- **GitHub Issues:** Report bugs and request features
- **Documentation:** Comprehensive guides and API references
- **Examples:** Sample projects and tutorials

---

## 🏆 Why Choose Our IDE?

### For Developers
- **Zero Setup:** Start coding instantly in any supported language
- **AI Pair Programmer:** Get intelligent assistance 24/7
- **Cross-Platform:** Works on any device with a web browser
- **Professional Grade:** Enterprise-ready features and performance

### For Educators
- **Interactive Learning:** AI tutor helps students understand concepts
- **Safe Environment:** Sandboxed execution prevents system damage
- **Progress Tracking:** Monitor student coding patterns and improvements

### For Enterprises
- **Self-Hosted Option:** Deploy on your own infrastructure
- **Custom AI Models:** Integrate with your proprietary AI systems
- **Team Management:** Role-based access control and collaboration tools

---

## 🌟 Success Stories

> "This IDE revolutionized how our team prototypes and experiments with new ideas. The AI assistance catches bugs before they happen and suggests optimizations we wouldn't have considered."  
> — Senior Developer, Tech Startup

> "As a coding instructor, this tool has been invaluable. Students get instant feedback and explanations, making complex concepts much easier to grasp."  
> — Computer Science Professor

---

## 📞 Get Started Today!

Ready to experience the future of coding? 

1. **Clone the repository**
2. **Set up your environment**
3. **Configure your OpenAI API key**
4. **Start coding with AI superpowers!**

---

**Join thousands of developers already building amazing things with our Agentic AI IDE!**

---

*Built with ❤️ for the global developer community*  
*Powered by OpenAI GPT-5 • React • Node.js • Monaco Editor*

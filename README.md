# 💬 WebSocket Chat Tester

A simple full-stack WebSocket chat application using **Django Channels** for the backend and a clean, responsive **HTML + JavaScript** frontend to test WebSocket communication in real-time.

> 🔧 Ideal for testing and debugging Django Channels-based WebSocket APIs.

---

## 🚀 Tech Stack

### 🔹 Backend
- Python 3.10+
- Django 4.x
- Django Channels
- Redis (for channel layer)
- PostgreSQL (optional; default: SQLite for development)

### 🔹 Frontend
- HTML5, CSS3
- Vanilla JavaScript (WebSocket API)
- Responsive, modern UI

---

## 📁 Folder Structure

WebSocketTest/
├── backend/ # Django project folder
│ └── chat/ # Django app with consumers
├── frontend/
│ ├── index.html # Frontend WebSocket client
│ └── style.css # Modern CSS styling
├── README.md

yaml
Copy
Edit

---

## 🔧 Backend Setup (Django + Channels)

> Make sure Python and Redis are installed.

### 1. Clone the repository

```bash
git clone https://github.com/your-username/websocket-chat-tester.git
cd websocket-chat-tester/backend
2. Create virtual environment
bash
Copy
Edit
python -m venv env
source env/bin/activate    # On Windows: env\Scripts\activate
3. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
requirements.txt should include:

django

channels

channels_redis

daphne

psycopg2-binary (optional for PostgreSQL)

4. Start Redis server
bash
Copy
Edit
redis-server
5. Run migrations and start the server
bash
Copy
Edit
python manage.py migrate
python manage.py runserver
6. WebSocket endpoint example
ruby
Copy
Edit
ws://127.0.0.1:8000/ws/chat/room1/
This is defined in routing.py and handled by ChatConsumer.

🎨 Frontend Setup
1. Open the frontend folder
bash
Copy
Edit
cd ../frontend
2. Edit WebSocket URL in index.html
Update the following line to match your backend WebSocket endpoint:

js
Copy
Edit
const wsUrl = 'ws://127.0.0.1:8000/ws/chat/room1/';
3. Open index.html in browser
Double-click the file or run a local server:

bash
Copy
Edit
# Optional: Run a simple server (Python 3.x)
python -m http.server 8080
Visit: http://localhost:8080/index.html

💡 How It Works
On page load, a WebSocket connection is established.

You can type messages into the input field.

The message is sent as a JSON object ({ "message": "hi" }) to the backend.

The backend echoes it to all users in the room via Redis and Channels group.

Messages from the server are displayed in the chat UI.

📸 Screenshots (optional)
Paste screenshots here for frontend UI and terminal logs

🧠 To-Do / Future Enhancements
 Add authentication

 Support multiple rooms via dropdown

 Save chat history to database

 UI animations and toast notifications

🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

📃 License


🙏 Acknowledgments
Django Channels Documentation

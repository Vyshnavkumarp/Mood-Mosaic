# Mood Mosaic 🌈

A web application for tracking emotional patterns, generating daily reflections, and receiving weekly AI-powered insights to promote self-awareness and emotional well-being.

![Demo Preview](https://github.com/user-attachments/assets/59e7fb8c-dc88-42ec-aa0e-14e55824c7c4)  

## Features ✨
- **Daily Mood Tracking**: Log moods with reasons using an intuitive visual interface
- **AI-Powered Insights**: 
  - Daily reflections comparing today's mood with yesterday
  - Weekly summaries analyzing patterns using Google's Gemini AI
- **Mood Calendar**: Visual heatmap showing emotional trends over time
- **Secure Authentication**: User registration/login with password hashing
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Historical Data**: View/edit past entries with date picker functionality

## Technologies Used 🛠️
- **Backend**: Python/Flask, SQLite
- **AI Integration**: Google Gemini API
- **Frontend**: HTML/CSS, JavaScript, Heatmap.js
- **Scheduling**: APScheduler
- **Security**: PBKDF2 password hashing

## Installation & Setup 💻

### Prerequisites
- Python 3.8+
- Google Gemini API key ([Get API key](https://ai.google.dev/))
- pip package manager

### Steps
1. **Clone Repository**
   ```bash
   git clone https://github.com/yourusername/mood-mosaic.git
   cd mood-mosaic
   ```

2. **Set Up Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Environment**
   - Create `.env` file:
     ```env
     FLASK_SECRET_KEY=your_random_secret_string
     GEMINI_API_KEY=your_google_gemini_key
     ```
   - Update `app.py`:
     ```python
     app.secret_key = os.getenv("FLASK_SECRET_KEY")
     genai.configure(api_key=os.getenv("GEMINI_API_KEY"))
     ```

5. **Initialize Database**
   ```bash
   flask run  # Creates database tables automatically
   ```

6. **Run Application**
   ```bash
   flask run --debug
   ```

Visit `http://localhost:5000` in your browser to access the app!

## Usage Guide 🚀

1. **Registration & Login**
   - Create an account via `/register`
   - Log in with credentials at `/login`

2. **Daily Mood Entry**
   - Navigate to `/mood_input`
   - Select mood emoji (Sad 😢 → Excited 🎉)
   - Add optional reason
   - Get instant AI-generated daily insight

3. **Weekly Insights**
   - Access `/insights` to view:
     - Mood patterns analysis
     - Comparative trends
     - Personalized suggestions
   - Insights auto-generate every Sunday

4. **Calendar Heatmap**
   - Visualize mood history on interactive calendar
   - Hover over dates to see historical entries

5. **Edit Previous Entries**
   - Use date picker to navigate different days
   - Update existing entries anytime

## Project Structure 📂

```
mood-mosaic/
├── app.py                 # Main application logic
├── requirements.txt       # Dependencies
├── script.js              # Frontend interactions
├── templates/             # HTML templates
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── mood_input.html
│   └── insights.html
├── static/                # CSS/JS assets
└── mood_tracker.db        # SQLite database (auto-created)
```

## Configuration ⚙️

Customize in `app.py`:
- `DATABASE = 'mood_tracker.db'` → Change database name
- `timedelta(days=365)` → Adjust calendar heatmap range
- Mood options in `mood_map` (line 155)

## Troubleshooting 🔧

Common Issues:
- **Missing Dependencies**: Run `pip install -r requirements.txt`
- **API Errors**: Verify Gemini API key in `.env`
- **Database Issues**: Delete `mood_tracker.db` and restart app
- **Empty Heatmap**: Ensure mood entries exist for current date range

## Acknowledgments 🙏

- Google Gemini API for AI insights
- Flask community for web framework
- APScheduler for background tasks

---

**Happy Mood Tracking!** 🌟  
*Remember: Every mood matters in your mosaic of emotions.*

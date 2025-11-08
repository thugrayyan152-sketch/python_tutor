# 🎓 Python Tutor - AI-Powered Learning Platform

An intelligent Python learning platform powered by OpenAI GPT-4o-mini, featuring personalized tutoring, performance tracking, and comprehensive educational tools for both students and teachers.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-3.0.0-green.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Table of Contents
- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### 🎓 Student Dashboard (8 Features)

1. **📚 Learning Path**
   - Structured curriculum organized by difficulty levels (Basic, Intermediate, Advanced)
   - 15 curated Python topics with explanations and video links
   - Progressive learning journey from fundamentals to advanced concepts

2. **🧠 Skill Tester**
   - Interactive diagnostic quiz with 10 randomized questions
   - AI-powered skill level assessment (Beginner/Intermediate/Advanced/Expert)
   - Instant feedback with correct answers

3. **🎙️ AI Tutor**
   - Real-time conversational AI powered by GPT-4o-mini
   - Ask any Python question and get detailed explanations
   - Code examples with syntax highlighting
   - Context-aware responses

4. **📓 Smart Notes Generator**
   - AI-generated comprehensive study notes on any Python topic
   - Includes definitions, key concepts, syntax, usage patterns
   - Code examples and common pitfalls
   - Exportable and formatted for easy reading

5. **✏️ Practice Exercises**
   - Curated coding challenges linked to specific topics
   - Randomized for variety
   - Covers all difficulty levels

6. **🐞 Code Debugger**
   - Paste problematic code with optional error messages
   - AI identifies issues and explains root causes
   - Provides corrected code with detailed explanations
   - Step-by-step debugging guidance

7. **🎥 Video Recommendations**
   - AI-powered video suggestions from verified channels
   - Channels: CodeWithHarry, Apna College, Ishan Sharma, Programming with Mosh, Jenny's Lectures CS IT, Bro Code
   - Search any Python topic for personalized recommendations
   - Pre-curated video library with clickable YouTube links
   - Real videos from popular educators

8. **📊 Performance Analyzer**
   - Comprehensive activity tracking dashboard
   - Visual statistics: questions asked, videos watched, tests taken, practice completed, notes generated
   - AI-powered performance analysis
   - Personalized recommendations and improvement areas
   - Recent activity timeline with timestamps
   - Motivational insights

### 👨‍🏫 Teacher Dashboard (3 Features)

1. **📝 Text Summarizer**
   - AI condenses long articles, papers, or educational content
   - Generates 3-5 key bullet points
   - Highlights important terms
   - Perfect for quick lesson prep

2. **📘 Lesson Planner**
   - Generates detailed 60-minute lesson plans
   - Includes learning objectives, core concepts, code examples
   - Practice activities and assessment methods
   - Fully structured and ready to use

3. **🧪 Quiz Generator**
   - Creates comprehensive quizzes from lesson notes
   - 3 multiple-choice questions + 2 coding challenges
   - Properly formatted and numbered
   - Instant quiz creation from any content

## 🛠️ Technologies

### Backend
- **Flask 3.0.0** - Python web framework
- **SQLite** - Lightweight database
- **OpenAI API** - GPT-4o-mini for AI features

### Frontend
- **HTML5/CSS3** - Modern UI with glass-morphism design
- **JavaScript (Vanilla)** - Dynamic interactions
- **Jinja2** - Template engine

### Key Libraries
- `openai` - OpenAI API integration
- `functools` - Decorator utilities
- `sqlite3` - Database operations
- `random` - Content shuffling

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- OpenAI API key

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/python-tutor.git
cd python-tutor
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Set Up OpenAI API Key
Open `app.py` and replace the API key on line 16:
```python
OPENAI_API_KEY = 'your-openai-api-key-here'
```

**⚠️ Security Note:** For production, use environment variables:
```python
OPENAI_API_KEY = os.getenv('OPENAI_API_KEY')
```

### Step 4: Run the Application
```bash
python app.py
```

The application will start on `http://127.0.0.1:5000`

## ⚙️ Configuration

### Database Initialization
The database is automatically created on first run with sample data including:
- 15 Python topics (Basic to Advanced)
- 6 practice exercises
- 15 assessment questions
- Sample Q&A pairs

### Session Configuration
- Secret key: Set in `app.py` (line 11)
- Session-based authentication
- Role-based access control (Student/Teacher)

## 🚀 Usage

### For Students

1. **Register/Login**
   - Create an account or login
   - Select "Student" role

2. **Navigate Dashboard**
   - Access 8 powerful learning tools
   - Start with Learning Path for structured curriculum
   - Take Skill Test to assess current level

3. **Use AI Features**
   - Ask questions to AI Tutor
   - Generate smart notes on topics
   - Debug your code
   - Get video recommendations

4. **Track Progress**
   - Visit Performance Analyzer
   - View statistics and activity history
   - Get AI-powered insights and recommendations

### For Teachers

1. **Register/Login**
   - Create an account with "Teacher" role

2. **Create Content**
   - Summarize educational materials
   - Generate lesson plans for topics
   - Create quizzes from notes

3. **Use AI Tools**
   - All tools powered by GPT-4o-mini
   - Instant content generation
   - Professional formatting

## 📁 Project Structure

```
python_tutor/
├── app.py                          # Main Flask application
├── requirements.txt                # Python dependencies
├── README.md                       # This file
├── python_tutor.db                 # SQLite database (auto-generated)
│
├── templates/                      # HTML templates
│   ├── base.html                   # Base template with navigation
│   ├── home.html                   # Landing page
│   ├── login.html                  # Login page
│   ├── register.html               # Registration page
│   ├── dashboard.html              # Main dashboard (student/teacher)
│   │
│   ├── student/                    # Student templates
│   │   ├── learning_path.html
│   │   ├── skill_test.html
│   │   ├── voice_tutor.html
│   │   ├── smart_notes.html
│   │   ├── practice.html
│   │   ├── code_debug.html
│   │   ├── video_recommend.html
│   │   └── performance_analyzer.html
│   │
│   └── teacher/                    # Teacher templates
│       ├── summarizer.html
│       ├── lesson_planner.html
│       └── quiz_generator.html
│
└── static/                         # Static files
    ├── style.css                   # Main stylesheet
    └── (other static assets)
```

## 🔌 API Endpoints

### Student API Endpoints
- `POST /api/ask` - AI Tutor chat
- `POST /api/debug` - Code debugging
- `POST /api/notes` - Smart notes generation
- `POST /api/recommend-videos` - Video recommendations
- `POST /api/assess` - Skill assessment
- `POST /api/analyze-performance` - Performance analysis

### Teacher API Endpoints
- `POST /api/summarize` - Text summarization
- `POST /api/plan` - Lesson plan generation
- `POST /api/quiz` - Quiz generation

### Authentication
- `POST /login` - User login
- `POST /register` - User registration
- `GET /logout` - User logout

## 🎨 Features Highlight

### Activity Tracking
All student activities are automatically tracked:
- Questions asked to AI Tutor
- Videos watched
- Skill tests taken
- Practice exercises completed
- Notes generated
- Code debugging sessions

### AI-Powered Analysis
Performance Analyzer provides:
- Overall performance summary
- Identified strengths
- Areas for improvement
- 3-5 personalized recommendations
- Motivational messages

### Video Recommendations
Curated from verified channels:
- **CodeWithHarry** - Hindi/English tutorials
- **Apna College** - Shradha Khapra's content
- **Ishan Sharma** - Career guidance
- **Programming with Mosh** - Professional courses
- **Jenny's Lectures CS IT** - CS fundamentals
- **Bro Code** - Beginner-friendly tutorials

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- OpenAI for GPT-4o-mini API
- Flask community for excellent documentation
- All the YouTube educators featured in video recommendations

## 📧 Contact

For questions or support, please open an issue on GitHub.

---

**Made with ❤️ for Python learners everywhere**

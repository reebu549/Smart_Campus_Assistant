# Smart Campus Assistant
### An AI-Powered Academic Assistant for University Students

Smart Campus Assistant is an AI-powered academic assistant designed to simplify everyday university activities. It helps students access academic schedules, check laboratory availability, arrange instructor meetings, and submit campus complaints through natural language conversations.

Instead of navigating multiple portals, documents, and administrative processes, students can interact with one intelligent assistant.

## The Problem

University students often face difficulties accessing academic information and managing routine campus activities.

Finding class schedules, checking lab availability, arranging meetings with instructors, and reporting campus issues can involve multiple steps and disconnected resources.

**The goal:** Build a centralized, conversational assistant that makes these processes easier and more accessible.

## Key Features

### Academic Information
- Supports multiple degree programs, including BSCS, BSIT, BSDS, BSSE, BSCYS, and BSAI.
- Semester-based academic information.
- Displays subjects and their respective instructors.
- Uses real university timetable data structured in JSON format.

### Class Schedule
- Displays organized class schedules.
- Provides subject, instructor, timing, and room information where available.

### Lab Availability
- Checks laboratory availability.
- Identifies available and occupied time slots using timetable information.

### Instructor Meetings
- Checks instructor availability.
- Identifies suitable meeting slots.
- Books meetings through Google Calendar.
- Lists previously scheduled meetings.
- Cancels existing meetings.
- Prevents scheduling conflicts by checking office hours, teaching schedules, existing meetings, and calendar availability.

### AI-Powered Assistant
- Understands natural language queries.
- Identifies user intent and selects appropriate tools.
- Handles relative dates such as "tomorrow."
- Requests clarification when required information is missing.
- Provides conversational responses based on actual tool execution results.

### Campus Complaints
- Allows students to submit campus-related complaints.
- Stores submitted complaints in a JSON file.

## How the AI Agent Works

The project uses **LLM-based function/tool calling** to connect natural language interaction with Python functions.

The workflow:

1. A student sends a message through the chat interface.
2. Groq LLM interprets the request.
3. The model selects the appropriate tool and provides its required arguments.
4. Python executes the selected function.
5. The function returns its result to the LLM.
6. The assistant generates a natural-language response.

**Important:** The LLM does not directly execute Python code. It selects the appropriate function, while the Python backend performs the actual operation.

## System Architecture

```text
             Student
                |
                v
        Gradio User Interface
                |
                v
          Groq LLM API
                |
          Tool Selection
                |
                v
         Python Backend
                |
       +--------+--------+
       |        |        |
       v        v        v
    Academic  Lab &    Meeting
     Data    Schedule  Management
       |        |        |
       v        v        v
      JSON    JSON   Google Calendar
                |
                v
         Tool Execution Result
                |
                v
          Groq LLM API
                |
                v
       Natural Language Response
```

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Backend logic and tool execution |
| Groq LLM API | Natural language understanding and tool calling |
| JSON | Structured academic data and complaint storage |
| Google Calendar API | Meeting creation, listing, and cancellation |
| Gradio | Interactive application interface |
| HTML / CSS | Custom user interface and styling |

## Core Python Tools

The assistant integrates eight Python tools:

1. Schedule retrieval
2. Course information retrieval
3. Laboratory availability checking
4. Instructor free-slot checking
5. Meeting booking
6. Meeting listing
7. Meeting cancellation
8. Complaint submission

## Getting Started

### Prerequisites

- Python 3.10+
- Groq API key
- Google Cloud project
- Google Calendar API enabled
- OAuth 2.0 credentials for Google Calendar

### Installation

Clone the repository:

```bash
git clone YOUR_REPOSITORY_URL
cd smart-campus-assistant
```

Create and activate a virtual environment:

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

### Environment Configuration

Create a `.env` file and configure your API credentials:

```env
GROQ_API_KEY=your_groq_api_key
```

Configure Google Calendar OAuth credentials according to the Google Cloud setup used by the project.

**Important:** Never upload API keys, OAuth client secrets, access tokens, or private credentials to GitHub.

### Run the Application

```bash
python app.py
```

Use the local Gradio URL displayed in the terminal to access the application.

*Note: Adjust the entry-point filename and configuration steps to match your actual project structure.*

## Project Data

The application uses structured JSON data containing university academic information, including:

- Degree programs
- Semester information
- Subjects
- Instructors
- Class schedules
- Laboratory schedules

The original timetable information was processed and organized into JSON format for application-level retrieval.

## Project Objective

This project explores how Large Language Models, function calling, structured data, and external APIs can work together to solve practical problems in an academic environment.

It demonstrates the integration of:

- AI Agent Development
- Natural Language Processing
- Python Backend Development
- API Integration
- Data Processing
- Interactive Application Development

## Future Improvements

- Student authentication and role-based access.
- Automated timetable updates.
- Additional departmental integrations.
- Improved administrative dashboards.
- Deployment for university-wide access.
- Enhanced complaint tracking and management.

## Developer

**Areeba Ahmad**

BS IT Graduate | Data Science & AI Enthusiast

Built with curiosity, creativity, and a passion for solving real-world problems.

---

⭐ If you find this project interesting, consider starring the repository!

# 🤖 FullStack AI Blog Generator

A production-ready web application built with Django that generates blog posts from YouTube video transcripts using AI. Users can input a YouTube video URL, transcribe the audio with AssemblyAI, and generate comprehensive blog articles using OpenAI's `text-davinci-003` model. The app supports user authentication, blog management, and a PostgreSQL database, making it ideal for content creators, developers, or as a base for AI-driven SaaS products.

## 📦 Features

* 🔐 **User Authentication**: Registration, login, logout, and user-specific blog management
* 🎥 **YouTube Transcription**: Extracts audio from YouTube videos and transcribes it using AssemblyAI
* ✍️ **AI Blog Generation**: Creates SEO-optimized blog articles from transcripts using OpenAI
* 📋 **Blog Management**: View, save, and access detailed blog posts tied to user accounts
* 💾 **Database Storage**: Stores blog posts with metadata in PostgreSQL
* 🖼️ **Responsive Frontend**: Django templates with a clean, user-friendly interface
* 📊 **Admin Dashboard**: Customized Django admin for managing blog posts and users
* 📂 **Modular App Structure**: Clean separation of concerns for scalability

## 🧰 Tech Stack

| Layer         | Technology                           |
|---------------|--------------------------------------|
| Backend       | Django (Python 3.8+)                |
| AI Services   | AssemblyAI, OpenAI (text-davinci-003) |
| Frontend      | Django Templates (HTML, CSS)        |
| Database      | PostgreSQL                          |
| Dependencies  | pytube, assemblyai, openai, psycopg2 |
| Tools         | Git, pip                            |

## 🚀 Installation

1. **Clone the Repository**:
   ```
   git clone https://github.com/Upnit-b/FullStack-AI-Blog-Generator.git
   cd FullStack-AI-Blog-Generator/src
   ```

2. **Create and Activate a Virtual Environment**:
   ```
   python -m venv env
   source env/bin/activate  # Windows: env\Scripts\activate
   ```

3. **Install Dependencies**:
   ```
   pip install django pytube assemblyai openai psycopg2-binary
   ```

4. **Set Up PostgreSQL Database**:
   - Create a database (e.g., using `psql` or pgAdmin):
     ```
     CREATE DATABASE ai_blog_generator;
     ```

5. **Configure Environment Variables**:
   - Create a `.env` file in the `src` directory:
     ```
     DJANGO_SECRET_KEY=your_django_secret_key
     AAI_API=your_assemblyai_api_key
     OPENAI_API=your_openai_api_key
     DB_NAME=ai_blog_generator
     DB_USERNAME=your_postgres_username
     DB_PASSWORD=your_postgres_password
     DB_HOST=localhost
     DB_PORT=5432
     ```

6. **Apply Migrations**:
   ```
   python manage.py migrate
   ```

7. **Create a Superuser**:
   ```
   python manage.py createsuperuser
   ```

8. **Run the Development Server**:
   ```
   python manage.py runserver
   ```

## 📝 Blog Generation

The app generates blog posts from YouTube videos:

* 🎥 **Input**: Provide a YouTube video URL via the homepage form
* 🔊 **Transcription**: Audio is downloaded and transcribed using AssemblyAI
* ✍️ **AI Processing**: OpenAI generates a blog article from the transcript
* 💾 **Storage**: Blog posts are saved with metadata (title, link, content) in PostgreSQL

## 🔐 Authentication

The app supports:

* 🔐 **Signup/Login**: Create accounts and log in to manage blogs
* 🔒 **Access Control**: Only authenticated users can generate and view their blogs
* 🚪 **Logout**: Securely log out to end sessions

## 🗂️ Project Structure

```
src/
├── ai_app/              # Main project settings
│   ├── __init__.py
│   ├── asgi.py         # ASGI configuration
│   ├── wsgi.py         # WSGI configuration
│   ├── settings.py     # Django settings (PostgreSQL, templates)
│   ├── urls.py         # Project-level URL routing
├── blog_generator/      # Blog generation app
│   ├── __init__.py
│   ├── admin.py        # Admin configuration for BlogPost
│   ├── apps.py        # App configuration
│   ├── models.py      # BlogPost model
│   ├── tests.py       # Placeholder for tests
│   ├── urls.py        # App-specific URL routes
│   ├── views.py       # Blog generation and authentication logic
├── templates/           # HTML templates (index.html, login.html, etc.)
├── media/               # Downloaded YouTube audio files
├── static/              # Static files (CSS, JS)
├── manage.py            # Django management script
└── requirements.txt     # Python dependencies
```

## 🛠 Admin Dashboard

The admin panel is customized:

* 📋 View and manage `BlogPost` entries and users
* 🔍 Filter blog posts by user or creation date
* ✏️ Edit blog post details directly in the admin interface

## 📬 Contact

Built by @Upnit-b — feel free to reach out via [GitHub Issues](https://github.com/Upnit-b/FullStack-AI-Blog-Generator/issues) for suggestions or bugs.

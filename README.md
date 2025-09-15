# Todo & Notes App

A modern, containerized todo and notes application with PostgreSQL backend.

## Features

- ✨ Beautiful, animated UI
- 📋 Todo management with completion tracking
- 📝 Quick notes with timestamps
- 🐳 Fully containerized with Docker
- 🔒 Secure credential management
- 🚀 Easy deployment

## Quick Start

### Prerequisites

- Docker & Docker Compose
- Node.js (v16 or higher)
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/todo-notes-app.git
   cd todo-notes-app
   ```

2. **Set up environment variables:**
   ```bash
   cp .env.example .env
   # Edit .env with your actual credentials
   nano .env
   ```

3. **Start the database:**
   ```bash
   docker-compose up -d
   ```

4. **Install dependencies and start the API:**
   ```bash
   npm install
   mkdir public
   # Place your index.html in the public folder
   npm start
   ```

5. **Access the app:**
   Open http://localhost:3000 in your browser

## Environment Variables

Copy `.env.example` to `.env` and update the following:

- `POSTGRES_PASSWORD`: Strong password for PostgreSQL
- `DB_PASSWORD`: Same as POSTGRES_PASSWORD
- `JWT_SECRET`: Random string for future authentication
- `PORT`: API server port (default: 3000)

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/todos` | Get all todos |
| POST | `/api/todos` | Create new todo |
| PUT | `/api/todos/:id` | Update todo |
| DELETE | `/api/todos/:id` | Delete todo |
| GET | `/api/notes` | Get all notes |
| POST | `/api/notes` | Create new note |
| DELETE | `/api/notes/:id` | Delete note |
| GET | `/health` | Health check |

## Docker Commands

```bash
# Start services
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs -f

# Restart database
docker-compose restart postgres

# Access database directly
docker exec -it todo_notes_db psql -U todouser -d todo_notes
```

## Security

- Never commit `.env` files to Git
- Use strong passwords (included example generates 43-character password)
- Consider setting up SSL/TLS for production
- Implement authentication for multi-user support

## Production Deployment

1. Update environment variables for production
2. Set up reverse proxy (nginx recommended)
3. Enable SSL certificates
4. Configure firewall rules
5. Set up automated backups

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - see LICENSE file for details

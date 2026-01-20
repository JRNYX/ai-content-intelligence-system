# 🎬 AI Content Intelligence System

**Complete AI-powered content intelligence, strategy, and production system for YouTube/Instagram creators**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104-green.svg)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-18-blue.svg)](https://react.dev/)

## 🚀 Features

### 7 Integrated Modules

- **Discovery & Analysis** - Find and analyze viral competitor content
- - **Strategic Intelligence** - Map trends to your brand, identify opportunities
  - - **Content Planning** - Generate data-driven 30/60/90-day content calendars
    - - **Script Generation** - AI writes viral-optimized scripts
      - - **Collaborative Editing** - Real-time script editing with version control
        - - **Production Breakdown** - Auto-generate shot lists, storyboards, checklists
          - - **Performance Tracking** - Track, predict, and learn from content performance
           
            - ### Flexible Transcription Options
           
            - Choose your transcription service based on needs and budget:
           
            - - **Whisper API** (Recommended) - $0.006/min, ~$2.40 for 100 60-second reels
              - - **Local Whisper** (Free) - No cost, runs locally with GPU support
                - - **AssemblyAI** (Premium) - $0.15-0.30/file, advanced features (speaker diarization, sentiment)
                 
                  - ## 🛠 Tech Stack
                 
                  - ### Backend
                  - - FastAPI (async Python framework)
                    - - SQLAlchemy + PostgreSQL (database)
                      - - Celery + Redis (background jobs & caching)
                        - - Claude AI API (content analysis & generation)
                          - - Multiple transcription services (flexible integration)
                           
                            - ### Frontend
                            - - Next.js 14 (React framework)
                              - - TypeScript (type safety)
                                - - Tailwind CSS (styling)
                                  - - shadcn/ui (components)
                                    - - Recharts (analytics & visualizations)
                                     
                                      - ### Infrastructure
                                      - - Docker & Docker Compose
                                        - - Redis (cache & queue)
                                          - - PostgreSQL (primary database)
                                            - - Celery workers (async processing)
                                             
                                              - ## 📦 Quick Start
                                             
                                              - ### Prerequisites
                                              - - Docker & Docker Compose (easiest), OR
                                                - - Python 3.11+
                                                  - - Node.js 18+
                                                    - - PostgreSQL (optional if using SQLite)
                                                     
                                                      - ### Option 1: Docker (Recommended)
                                                     
                                                      - ```bash
                                                        # Clone repository
                                                        git clone https://github.com/yourusername/ai-content-intelligence-system.git
                                                        cd ai-content-intelligence-system

                                                        # Copy environment template
                                                        cp backend/.env.example backend/.env
                                                        # Edit backend/.env with your API keys

                                                        # Start everything with Docker Compose
                                                        docker-compose up -d

                                                        # Access application
                                                        # Frontend: http://localhost:3000
                                                        # Backend API: http://localhost:8000
                                                        # API Docs: http://localhost:8000/docs
                                                        ```

                                                        ### Option 2: Local Development

                                                        **Backend:**
                                                        ```bash
                                                        cd backend
                                                        python -m venv venv
                                                        source venv/bin/activate  # or `venv\Scripts\activate` on Windows
                                                        pip install -r requirements.txt
                                                        python app/main.py
                                                        ```

                                                        **Frontend:**
                                                        ```bash
                                                        cd frontend
                                                        npm install
                                                        npm run dev
                                                        ```

                                                        **Access:** http://localhost:3000

                                                        ## 🔧 Configuration

                                                        ### Transcription Setup

                                                        The system supports three transcription services. Configure in Settings → Transcription:

                                                        #### Option 1: Whisper API (Default)
                                                        1. Get OpenAI API key from https://platform.openai.com/api-keys
                                                        2. 2. In app Settings, select "Whisper API"
                                                           3. 3. Enter API key
                                                              4. 4. Cost: ~$2.40/month for 100 60-second reels
                                                                
                                                                 5. #### Option 2: Local Whisper (Free)
                                                                 6. 1. Install ffmpeg:
                                                                    2.    - Mac: `brew install ffmpeg`
                                                                          -    - Linux: `apt-get install ffmpeg`
                                                                               -    - Windows: Download from ffmpeg.org
                                                                                    - 2. First transcription downloads model (~769MB)
                                                                                      3. 3. Optional: Install CUDA for GPU (10x faster)
                                                                                         4. 4. Cost: FREE
                                                                                           
                                                                                            5. #### Option 3: AssemblyAI (Premium)
                                                                                            6. 1. Get API key from https://www.assemblyai.com
                                                                                               2. 2. In app Settings, select "AssemblyAI"
                                                                                                  3. 3. Enable features: speaker diarization, sentiment, etc.
                                                                                                     4. 4. Cost: ~$15-30/month for 100 reels
                                                                                                       
                                                                                                        5. ### API Keys Required
                                                                                                       
                                                                                                        6. Create `.env` file in `backend/` directory:
                                                                                                       
                                                                                                        7. ```env
                                                                                                           # OpenAI (for Whisper API transcription)
                                                                                                           OPENAI_API_KEY=your_openai_api_key

                                                                                                           # Anthropic (for Claude API content analysis)
                                                                                                           ANTHROPIC_API_KEY=your_anthropic_api_key

                                                                                                           # Apify (for Instagram scraping)
                                                                                                           APIFY_API_KEY=your_apify_api_key

                                                                                                           # Optional: AssemblyAI (for premium transcription)
                                                                                                           ASSEMBLYAI_API_KEY=your_assemblyai_api_key

                                                                                                           # JWT Secret (generate with: openssl rand -hex 32)
                                                                                                           SECRET_KEY=your_secret_key_here

                                                                                                           # Database (PostgreSQL recommended for production)
                                                                                                           DATABASE_URL=postgresql://user:password@localhost/content_db
                                                                                                           # Or use SQLite for development:
                                                                                                           # DATABASE_URL=sqlite:///./test.db

                                                                                                           # Redis
                                                                                                           REDIS_URL=redis://localhost:6379/0
                                                                                                           ```
                                                                                                           
                                                                                                           ## 📊 Cost Breakdown
                                                                                                           
                                                                                                           **Monthly costs for 400 reels/month:**
                                                                                                           
                                                                                                           | Setup | Transcription | Scraping | Claude API | **Total** |
                                                                                                           |-------|---------------|----------|-----------|-----------|
                                                                                                           | Budget | $9.60 (Whisper) | $15 | $8 | **$32.60** |
                                                                                                           | Free | FREE (Local) | $15 | $8 | **$23** |
                                                                                                           | Premium | $60-120 (AssemblyAI) | $15 | $8 | **$83-143** |
                                                                                                           
                                                                                                           ## 🏗 Project Structure
                                                                                                           
                                                                                                           ```
                                                                                                           content-intelligence-system/
                                                                                                           ├── frontend/              # Next.js React app
                                                                                                           │   ├── app/
                                                                                                           │   ├── components/
                                                                                                           │   ├── lib/
                                                                                                           │   ├── package.json
                                                                                                           │   └── tsconfig.json
                                                                                                           ├── backend/               # FastAPI Python app
                                                                                                           │   ├── app/
                                                                                                           │   │   ├── models/       # SQLAlchemy models
                                                                                                           │   │   ├── routers/      # API endpoints
                                                                                                           │   │   ├── services/     # Business logic
                                                                                                           │   │   │   └── transcription/  # Transcription services
                                                                                                           │   │   ├── tasks/        # Celery jobs
                                                                                                           │   │   └── main.py
                                                                                                           │   ├── requirements.txt
                                                                                                           │   └── .env.example
                                                                                                           ├── docker-compose.yml
                                                                                                           ├── README.md
                                                                                                           └── DEPLOYMENT.md
                                                                                                           ```
                                                                                                           
                                                                                                           ## 🚀 Deployment
                                                                                                           
                                                                                                           ### Railway.app (Easiest)
                                                                                                           See DEPLOYMENT.md for step-by-step guide
                                                                                                           
                                                                                                           ### AWS, DigitalOcean, Render
                                                                                                           See DEPLOYMENT.md for detailed instructions
                                                                                                           
                                                                                                           ## 📚 Documentation
                                                                                                           
                                                                                                           - [INSTALLATION.md](./INSTALLATION.md) - Detailed installation guide
                                                                                                           - - [DEPLOYMENT.md](./DEPLOYMENT.md) - Production deployment
                                                                                                             - - [API_DOCS.md](./docs/API_DOCS.md) - Complete API reference
                                                                                                               - - [TRANSCRIPTION_GUIDE.md](./docs/TRANSCRIPTION_GUIDE.md) - Transcription setup
                                                                                                                
                                                                                                                 - ## 🔐 Security
                                                                                                                
                                                                                                                 - - JWT authentication for all API endpoints
                                                                                                                   - - Rate limiting enabled
                                                                                                                     - - CORS properly configured
                                                                                                                       - - Environment variables for all secrets
                                                                                                                         - - SQL injection protection (SQLAlchemy)
                                                                                                                           - - HTTPS recommended for production
                                                                                                                            
                                                                                                                             - ## 🤝 Support
                                                                                                                            
                                                                                                                             - - 📖 [Documentation](./docs)
                                                                                                                               - - 🐛 [GitHub Issues](../../issues)
                                                                                                                                 - - 💬 [GitHub Discussions](../../discussions)
                                                                                                                                  
                                                                                                                                   - ## 📝 License
                                                                                                                                  
                                                                                                                                   - This project is licensed under the MIT License - see the LICENSE file for details.
                                                                                                                                  
                                                                                                                                   - ## 🎯 Roadmap
                                                                                                                                  
                                                                                                                                   - - [ ] Team collaboration features
                                                                                                                                     - [ ] - [ ] AI-powered thumbnail generation
                                                                                                                                     - [ ] - [ ] Multi-language support
                                                                                                                                     - [ ] - [ ] Advanced analytics dashboard
                                                                                                                                     - [ ] - [ ] TikTok integration
                                                                                                                                     - [ ] - [ ] YouTube Shorts integration
                                                                                                                                     - [ ] - [ ] Bulk content scheduling
                                                                                                                                    
                                                                                                                                     - [ ] ## 🙋 Contributing
                                                                                                                                    
                                                                                                                                     - [ ] Contributions are welcome! Please feel free to submit a Pull Request.
                                                                                                                                    
                                                                                                                                     - [ ] ---
                                                                                                                                    
                                                                                                                                     - [ ] **Built with ❤️ for content creators**
                                                                                                                                    
                                                                                                                                     - [ ] Get started now: `docker-compose up -d` 🚀

# ⚡ QUICK START - 5 MINUTES TO RUNNING

## 🚀 Fastest Way to Get Started

This guide gets your AI Content Intelligence System running in **under 5 minutes** with Docker.

---

## STEP 1: Clone the Repository (1 minute)

```bash
git clone https://github.com/JRNYX/ai-content-intelligence-system.git
cd ai-content-intelligence-system
```

---

## STEP 2: Get Your API Keys (2 minutes)

You need 2 API keys. Pick ONE transcription service:

### 🎯 **OPTION A: Whisper API (Recommended - Easiest)**

1. Go to: https://platform.openai.com/api-keys
2. 2. Create new API key (copy it)
   3. 3. Go to: https://console.anthropic.com
      4. 4. Create Anthropic API key (copy it)
        
         5. ### OR 🎯 **OPTION B: Local Whisper (Free - No API needed)**
        
         6. Just need the Anthropic key from step 3 above.
        
         7. ### OR 🎯 **OPTION C: AssemblyAI (Premium)**
        
         8. 1. Go to: https://www.assemblyai.com
            2. 2. Create API key (copy it)
               3. 3. Get Anthropic key too
                 
                  4. ---
                 
                  5. ## STEP 3: Create Environment File (1 minute)
                 
                  6. ```bash
                     # Create .env file
                     cp backend/.env.example backend/.env
                     ```

                     Edit `backend/.env` and add your keys:

                     ```env
                     # Minimal setup (WHISPER API OPTION)
                     OPENAI_API_KEY=sk-xxxxxxxxxxxx
                     ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxx

                     # OR for LOCAL WHISPER (only needs Anthropic)
                     ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxx
                     TRANSCRIPTION_SERVICE=local_whisper

                     # OR for ASSEMBLYAI
                     ASSEMBLYAI_API_KEY=xxxxxxxxxxxx
                     ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxx
                     TRANSCRIPTION_SERVICE=assemblyai
                     ```

                     ---

                     ## STEP 4: Start Everything (1 minute)

                     ```bash
                     docker-compose up -d
                     ```

                     **That's it!** Your system is running!

                     ---

                     ## ✅ Access Your System

                     ```
                     Frontend:     http://localhost:3000
                     Backend API:  http://localhost:8000
                     API Docs:     http://localhost:8000/docs
                     ```

                     **Default login credentials (set in system):**
                     - Email: `user@example.com`
                     - - Password: `password`
                      
                       - ---

                       ## 🔍 Verify Everything is Running

                       ```bash
                       # Check all containers are up
                       docker-compose ps

                       # Should show:
                       # - postgres    ✓ healthy
                       # - redis       ✓ healthy
                       # - backend     ✓ running
                       # - celery_worker ✓ running
                       # - frontend    ✓ running
                       ```

                       ---

                       ## 🎬 First Steps in the App

                       1. **Go to http://localhost:3000**
                       2. 2. **Settings > Transcription**
                          3.    - Choose your transcription service
                                -    - Add API key if needed
                                     -    - Test transcription with sample audio
                                          - 3. **Discovery**
                                            4.    - Search Instagram accounts or keywords
                                                  -    - System will analyze viral content
                                                       - 4. **Strategy**
                                                         5.    - Set up your brand pillars
                                                               -    - Define target audience
                                                                    - 5. **Start creating!**
                                                                     
                                                                      6. ---
                                                                     
                                                                      7. ## 📊 Architecture Overview
                                                                     
                                                                      8. ```
                                                                         ┌─────────────────────────────────────────┐
                                                                         │          Frontend (Next.js)             │
                                                                         │      http://localhost:3000              │
                                                                         └──────────────────┬──────────────────────┘
                                                                                            │
                                                                                            ↓
                                                                         ┌─────────────────────────────────────────┐
                                                                         │      Backend API (FastAPI)              │
                                                                         │      http://localhost:8000              │
                                                                         │   - Discovery & Analysis                │
                                                                         │   - Content Planning                    │
                                                                         │   - Script Generation (Claude API)      │
                                                                         └──────────────────┬──────────────────────┘
                                                                                            │
                                                                               ┌────────────┼────────────┐
                                                                               ↓            ↓            ↓
                                                                         ┌──────────┐ ┌──────────┐ ┌──────────┐
                                                                         │ Database │ │  Redis   │ │  Celery  │
                                                                         │(Postgres)│ │  Cache   │ │ Workers  │
                                                                         └──────────┘ └──────────┘ └──────────┘

                                                                         Transcription: Whisper API / Local / AssemblyAI
                                                                         AI Analysis: Claude API (Anthropic)
                                                                         ```

                                                                         ---

                                                                         ## 🔐 Security Notes

                                                                         - All API keys stored in `.env` (never committed)
                                                                         - - JWT authentication on all endpoints
                                                                           - - CORS configured for localhost
                                                                             - - Change `SECRET_KEY` in production
                                                                              
                                                                               - ---

                                                                               ## 🛠 Common Commands

                                                                               ```bash
                                                                               # View logs
                                                                               docker-compose logs -f backend

                                                                               # Stop everything
                                                                               docker-compose down

                                                                               # Restart
                                                                               docker-compose restart

                                                                               # Reset everything (⚠️ deletes data)
                                                                               docker-compose down -v
                                                                               docker-compose up -d

                                                                               # Access database
                                                                               docker exec -it content-intelligence-postgres psql -U postgres -d content_intelligence

                                                                               # Access backend shell
                                                                               docker exec -it content-intelligence-backend bash
                                                                               ```

                                                                               ---

                                                                               ## 🚨 Troubleshooting

                                                                               ### "Port 3000 already in use"
                                                                               ```bash
                                                                               # Change port in docker-compose.yml
                                                                               # Change "3000:3000" to "3001:3000" (or any free port)
                                                                               ```

                                                                               ### "API connection refused"
                                                                               ```bash
                                                                               # Check backend is running
                                                                               docker-compose logs backend

                                                                               # Restart backend
                                                                               docker-compose restart backend
                                                                               ```

                                                                               ### "Database connection error"
                                                                               ```bash
                                                                               # Check postgres is healthy
                                                                               docker-compose ps

                                                                               # If not healthy, restart
                                                                               docker-compose restart postgres
                                                                               ```

                                                                               ### "Transcription failing"
                                                                               ```bash
                                                                               # Check your API key is correct in Settings > Transcription
                                                                               # Test with sample audio first
                                                                               # Check logs: docker-compose logs backend
                                                                               ```

                                                                               ---

                                                                               ## 📈 Next Steps

                                                                               1. **Read the full README.md** for all features
                                                                               2. 2. **Check API_DOCS.md** for API reference
                                                                                  3. 3. **See TRANSCRIPTION_GUIDE.md** for transcription setup details
                                                                                     4. 4. **Explore the Dashboard** - all 7 modules waiting for you!
                                                                                       
                                                                                        5. ---
                                                                                       
                                                                                        6. ## 💰 Monthly Costs (Examples)
                                                                                       
                                                                                        7. ### Budget Setup (Whisper API)
                                                                                        8. - Transcription: $9.60/month (400 reels)
                                                                                           - - Claude API: $8/month
                                                                                             - - Instagram scraping: $15/month (Apify)
                                                                                               - - **TOTAL: ~$33/month**
                                                                                                
                                                                                                 - ### Free Setup (Local Whisper)
                                                                                                 - - Transcription: FREE
                                                                                                   - - Claude API: $8/month
                                                                                                     - - Instagram scraping: $15/month
                                                                                                       - - **TOTAL: ~$23/month**
                                                                                                        
                                                                                                         - ### Premium Setup (AssemblyAI)
                                                                                                         - - Transcription: $60-120/month
                                                                                                           - - Claude API: $8/month
                                                                                                             - - Instagram scraping: $15/month
                                                                                                               - - **TOTAL: ~$83-143/month**
                                                                                                                
                                                                                                                 - ---
                                                                                                                 
                                                                                                                 ##  Need Help?
                                                                                                                 
                                                                                                                 - 📖 Full docs in `/docs` folder
                                                                                                                 - - 🐛 GitHub Issues for bugs
                                                                                                                   - - 💬 GitHub Discussions for questions
                                                                                                                     - - 🔗 Check README.md for links
                                                                                                                      
                                                                                                                       - ---
                                                                                                                       
                                                                                                                       **You're all set! Your AI Content Intelligence System is running! 🎉**
                                                                                                                       
                                                                                                                       Start by navigating to http://localhost:3000 and exploring the app.
                                                                                                                       
                                                                                                                       Good luck creating viral content! 🚀    

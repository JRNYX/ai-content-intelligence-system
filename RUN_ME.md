# 🚀 RUN ME NOW - 4 COMMANDS TO LAUNCH

**Want to get this running RIGHT NOW?** Copy and paste these 4 commands.

---

## STEP 1: Clone the Repository

```bash
git clone https://github.com/JRNYX/ai-content-intelligence-system.git
cd ai-content-intelligence-system
```

---

## STEP 2: Set Up Your API Keys

### Get your FREE keys (2 minutes):

**OpenAI Key** (for Whisper transcription):
- Go to: https://platform.openai.com/api-keys
- - Create a key → Copy it
 
  - **Anthropic Key** (for Claude AI):
  - - Go to: https://console.anthropic.com
    - - Create a key → Copy it
     
      - ### Add keys to .env file:
     
      - ```bash
        cp backend/.env.example backend/.env
        ```

        Edit `backend/.env` and replace:
        ```
        OPENAI_API_KEY=your_key_here
        ANTHROPIC_API_KEY=your_key_here
        ```

        ---

        ## STEP 3: Start Everything with Docker

        ```bash
        docker-compose up -d
        ```

        **That's it!** Everything is running in the background.

        ---

        ## STEP 4: Access Your System

        **Open in your browser:**
        - **Frontend**: http://localhost:3000
        - - **API Docs**: http://localhost:8000/docs
          - - **Backend**: http://localhost:8000
           
            - **Default Login:**
            - - Email: `user@example.com`
              - - Password: `password`
               
                - ---

                ## ✅ System is Running!

                Your AI Content Intelligence System is now live.

                **Go to:**
                - http://localhost:3000
                - - Settings > Transcription
                  - - Choose your transcription service
                    - - Start creating viral content! 🎬
                     
                      - ---

                      ## 🛠 Common Issues?

                      **Port already in use?**
                      ```bash
                      # Change port in docker-compose.yml line 50
                      # 3000:3000  →  3001:3000
                      docker-compose down
                      docker-compose up -d
                      ```

                      **Database error?**
                      ```bash
                      docker-compose restart postgres
                      ```

                      **API not responding?**
                      ```bash
                      docker-compose logs backend
                      docker-compose restart backend
                      ```

                      ---

                      ## 📚 Learn More

                      - **Full Setup Guide**: See `QUICK_START.md`
                      - - **Features**: Check `README.md`
                        - - **API Reference**: Visit http://localhost:8000/docs
                         
                          - ---

                          **That's all! You're done! 🎉**

                          Enjoy your AI Content Intelligence System!

                          Questions? Check the docs or GitHub Issues.

                          Happy creating! 🚀

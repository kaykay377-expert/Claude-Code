# 🚀 Claude Code Quick Start

You have successfully set up Claude Code! Here's how to run it:

## ✅ Setup Complete

Your repository now has:
- ✅ API Key configured in GitHub Secrets
- - ✅ Project structure ready
  - - ✅ Dependencies configured in package.json
    - - ✅ Documentation and guides
     
      - ## 🎯 How to Run Claude Code
     
      - ### Option 1: Run Locally on Your Machine
     
      - ```bash
        # 1. Clone the repository
        git clone https://github.com/kaykay377-expert/Claude-Code.git
        cd Claude-Code

        # 2. Install dependencies
        npm install

        # 3. Copy the example env file
        cp .env.example .env

        # 4. Edit .env and add your Anthropic API key
        # Open .env and replace: your-api-key-here with your actual API key

        # 5. Make sure Claude Code CLI is installed
        brew install claude  # macOS/Linux
        # or for Windows: curl -fsSL https://claude.ai/install.sh | bash

        # 6. Authenticate with Claude
        claude

        # 7. Now you can run agents!
        npm run reviewer      # For PR reviews
        npm run ci-fixer      # For fixing CI failures
        npm run issue-handler # For handling issues
        ```

        ### Option 2: Run via GitHub Actions (Automated)

        Claude Code will automatically run when:

        1. **A Pull Request is created or updated**
        2.    - Claude reviews the code
              -    - Claude responds to reviewer feedback
               
                   - 2. **Tests fail in CI/CD**
                     3.    - Claude analyzes failure logs
                           -    - Claude fixes the code automatically
                            
                                - 3. **A GitHub Issue is created**
                                  4.    - Claude reads the requirements
                                        -    - Claude works on a solution
                                         
                                             - No action needed - it happens automatically!
                                         
                                             - ## 📝 Common Commands
                                         
                                             - ```bash
                                               # Review and fix code
                                               npm run reviewer

                                               # Fix CI/CD failures
                                               npm run ci-fixer

                                               # Handle GitHub issues
                                               npm run issue-handler

                                               # Advanced agent with custom permissions
                                               npm run dev

                                               # Monitor agent activity
                                               npm run monitor
                                               ```

                                               ## 🔑 API Key Location

                                               Your API key is stored securely in:
                                               - **GitHub Secrets** → `ANTHROPIC_API_KEY` (for GitHub Actions)
                                               - - **Your .env file** (for local development - NEVER commit this!)
                                                
                                                 - ## 📖 Next Steps
                                                
                                                 - 1. **Test locally first**: Run one of the commands above
                                                   2. 2. **Create a test PR** to see Claude in action
                                                      3. 3. **Check the Actions tab** to see workflow runs
                                                         4. 4. **Customize agents** in the `src/` folder as needed
                                                           
                                                            5. ## 🆘 Troubleshooting
                                                           
                                                            6. ### Error: "Claude Code not found"
                                                            7. - Install Claude Code CLI: `brew install claude`
                                                               - - Run `claude` to authenticate
                                                                
                                                                 - ### Error: "API key not found"
                                                                 - - For GitHub Actions: Check `Settings > Secrets > ANTHROPIC_API_KEY`
                                                                   - - For local: Create `.env` file with your API key
                                                                    
                                                                     - ### Error: "Permission denied"
                                                                     - - Ensure you have write access to the repository
                                                                       - - Check GitHub token permissions
                                                                        
                                                                         - ## 🎓 Learning More
                                                                        
                                                                         - - 📚 [Claude Agent SDK Docs](https://docs.anthropic.com/en/docs/claude-code/sdk/sdk-overview)
                                                                           - - 🔗 [GitHub Actions Docs](https://docs.github.com/en/actions)
                                                                             - - 💬 [Claude Code Support](https://support.anthropic.com)
                                                                              
                                                                               - ---

                                                                               **You're all set!** Start by running one of the commands above. Claude will handle the rest! 🤖

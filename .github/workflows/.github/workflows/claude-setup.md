# GitHub Actions Setup Guide for Claude Code

This directory contains GitHub Actions workflows that enable Claude Code to automatically review PRs, fix CI errors, and handle issues.

## Quick Setup Steps

### 1. Add Your API Key to GitHub Secrets

1. Go to your repository **Settings**
2. 2. Click **Secrets and variables > Actions**
   3. 3. Click **New repository secret**
      4. 4. Create a secret named: `ANTHROPIC_API_KEY`
         5. 5. Paste your API key from [console.anthropic.com](https://console.anthropic.com)
            6. 6. Click **Add secret**
              
               7. ### 2. Enable GitHub Actions
              
               8. 1. Go to the **Actions** tab in your repository
                  2. 2. Click **Enable Actions** (if not already enabled)
                     3. 3. Workflows will automatically run on PRs, pushes, and issues
                       
                        4. ### 3. Create Workflow Files
                       
                        5. Copy the workflow YAML files into this directory:
                       
                        6. - `claude-reviewer.yml` - Auto-reviews PRs and handles feedback
                           - - `claude-ci-fixer.yml` - Auto-fixes failing CI/CD tests
                             - - `claude-issue-handler.yml` - Handles GitHub issues
                              
                               - ## How the Workflows Work
                              
                               - ### PR Reviewer Workflow
                               - **Triggers on:** Pull request opened/updated, PR review comments
                              
                               - Claude will:
                               - 1. Read the PR changes
                                 2. 2. Analyze reviewer feedback (if any)
                                    3. 3. Make suggested fixes
                                       4. 4. Commit changes back to the PR branch
                                         
                                          5. ### CI Fixer Workflow
                                          6. **Triggers on:** Workflow failure (tests fail)
                                         
                                          7. Claude will:
                                          8. 1. Download CI failure logs
                                             2. 2. Analyze the error messages
                                                3. 3. Find the root cause in the code
                                                   4. 4. Fix the issues
                                                      5. 5. Re-run tests to verify
                                                        
                                                         6. ### Issue Handler Workflow
                                                         7. **Triggers on:** New issue created
                                                        
                                                         8. Claude will:
                                                         9. 1. Read the issue description
                                                            2. 2. Understand requirements
                                                               3. 3. Create a solution
                                                                  4. 4. Submit fixes via PR or commit
                                                                    
                                                                     5. ## Manual Testing
                                                                    
                                                                     6. To test Claude Code locally before using in GitHub Actions:
                                                                    
                                                                     7. ```bash
                                                                        # PR Review
                                                                        npm run reviewer

                                                                        # CI Fixing
                                                                        npm run ci-fixer

                                                                        # Issue Handling
                                                                        npm run issue-handler
                                                                        ```

                                                                        ## Configuration

                                                                        ### Environment Variables

                                                                        The workflows use these environment variables:

                                                                        - `ANTHROPIC_API_KEY` - Your Claude API key (GitHub Secret)
                                                                        - - `GITHUB_TOKEN` - Automatic token from GitHub Actions
                                                                          - - `ALLOWED_EDIT_PATHS` - Restrict Claude to specific directories
                                                                           
                                                                            - ### Customization
                                                                           
                                                                            - Edit the workflow files to:
                                                                            - - Change triggers (when workflows run)
                                                                              - - Modify Claude's permissions (what tools it can use)
                                                                                - - Update the prompt/instructions
                                                                                  - - Add approval gates
                                                                                   
                                                                                    - ## Troubleshooting
                                                                                   
                                                                                    - ### Workflows Not Running
                                                                                    - - Ensure GitHub Actions is enabled in Settings
                                                                                      - - Check that `ANTHROPIC_API_KEY` secret is created
                                                                                        - - Verify you have a paid Anthropic plan (free plans may have limits)
                                                                                         
                                                                                          - ### Claude Not Making Changes
                                                                                          - - Check the workflow logs in the Actions tab
                                                                                            - - Verify the API key is correct
                                                                                              - - Ensure Claude has permission to edit files
                                                                                                - - Review permission settings in the workflow YAML
                                                                                                 
                                                                                                  - ### Permission Denied Errors
                                                                                                  - - Use `gh` CLI to debug: `gh run view <run-id> --log`
                                                                                                    - - Check that the GitHub token has write access
                                                                                                      - - Verify branch protection rules aren't blocking changes
                                                                                                       
                                                                                                        - ## Learn More
                                                                                                       
                                                                                                        - - [Claude Agent SDK Docs](https://docs.anthropic.com/en/docs/claude-code/sdk/sdk-overview)
                                                                                                          - - [GitHub Actions Documentation](https://docs.github.com/en/actions)
                                                                                                            - - [Claude Code CLI Reference](https://www.anthropic.com/claude-code)

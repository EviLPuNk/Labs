1.Connecting github account through ssh (host machine)

    - Adding ssh pub key to git profile -> settings -> ssh and GPG keys -> add ssh keys.
    - Then go to host machine console and run ** ssh -vT git@github.com ** and press enter, once completed the command check
      That your username is successfully authenticated if yes then the ssh-key is working if no then recehck your ssh key (pub/private) and reauthenticate.
      Here is the resources to check:
            https://docs.github.com/en/authentication/troubleshooting-ssh/error-permission-denied-publickey
            https://docs.github.com/en/authentication/troubleshooting-ssh/error-host-key-verification-failed
    - Now, Once authenticated got to your git repo folder which was clone on your system; By using git clone your-repo-name.git
    - Then run command, git init
                        git pull
                        git fetch
                        git push
        But if you're getting an authentication failed error during git push and you're being asked for username/password, it means:
        
        ❌ You're pushing over HTTPS instead of SSH.
        Even though SSH is set up, Git is still trying to push via HTTPS.  

    - ✅ Solution: Change Your Git Remote to Use SSH Instead of HTTPS
            Run this command inside your Git repo: git remote set-url origin git@github.com:YOUR-USERNAME/your-repo-name.git
        
      🔁 Verify It: git remote -v
    
      It should now show: origin  git@github.com:YOUR-USERNAME/your-repo-name.git (fetch)
                          origin  git@github.com:YOUR-USERNAME/your-repo-name.git (push)
    
      ✅ Now Push: git push

      You should not be prompted for username/password anymore — it will use your SSH key.

2. Commands to be used for Daily-Workflow
    
    - ✅ 1. One-Time Setup (Global Git Config)
            
            git config --global user.name "YourGitHubUsername"
            git config --global user.email "youremail@example.com"

      To verify config:
            
            git config --global --list

    - 🔁 Daily Workflow: GitHub ↔ Local

        ✅ Step 1: Clone a GitHub Repo (only once)
            
            git clone git@github.com:YourUsername/your-repo.git
            cd your-repo

        ✅ Step 2: Pull Latest Code Before Working

            git pull origin main    | Replace main with your branch name if working on a different one.

        ✅ Step 3: Add New or Modified Files

            git status              | Check what's new/changed.

        ✅ Step 4: Commit Your Changes

            git commit -m "Your commit message here"

        ✅ Step 5: Push Changes to GitHub
        
            git push origin main    | Replace main with your branch name if working on a different one.

     🛠 Bonus Commands
        
        ✅ Create a New Branch
        
            git checkout -b new-feature

        ✅ Switch to a Branch

            git checkout main

        ✅ View Logs / History

            git log --oneline

        ✅ Undo a Change Before Committing

            git restore filename.txt

        
                                        📌 Cheat Sheet Summary

                            Task	                                Command
                    Set username & email	                git config --global user.name/email
                    Clone repo	                            git clone git@github.com:user/repo.git
                    Pull latest changes	                    git pull origin main
                    Check status	                        git status
                    Add file(s)	                            git add . or git add filename
                    Commit changes	                        git commit -m "message"
                    Push to GitHub	                        git push origin main
                    Check history	                        git log --oneline
                    Restore file (undo)	                    git restore filename

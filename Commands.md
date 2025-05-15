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

2.       

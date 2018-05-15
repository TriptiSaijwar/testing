Setting up two git accounts ON THE SAME SYSTEM.

Steps to manage multiple git accounts (eg. Work and Personal).
- https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574
- Add username and email for a particular Repo/project (Not Global)[Different for different git accounts].
    - git config user.name "TriptiSaijwar"
    - git config user.email tripti.tpt7@gmail.com

Use
- git config --list to know git configuration of a project.


Config File :
        
    # github
    Host Work
        HostName Work
        User git
        IdentityFile ~/.ssh/id_rsa
        IdentitiesOnly yes

    # github
    Host github-PERSONAL
        HostName github.com
        User git
        IdentityFile ~/.ssh/id_rsa_PERSONAL
        IdentitiesOnly yes
    
IdentitiesOnly yes  => (You can add IdentitiesOnly yes the SSH config block to force it to only use the IdentityFile you specified.)

If there comes error:
    - fatal: unable to access 'https://github-PERSONAL/TriptiSaijwar/testing.git/': Could not resolve host: github-PERSONAL
    
Solution:
- Go into the git folder created on the system
- (cmd + shift + .) to get the Hidden files.
- .git Folder => Config File

        [core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = true
        [remote "origin"]
        url = git@github-PERSONAL:TriptiSaijwar/testing.git
        fetch = +refs/heads/*:refs/remotes/origin/*
        [user]
        name = TriptiSaijwar
        email = tripti.tpt7@gmail.com




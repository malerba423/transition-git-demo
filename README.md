# steps to get set up for doing development

1. Install github desktop. You can use all the defaults when installing Github Desktop. Github desktop is just a GUI for git.

   > https://desktop.github.com/

2. Download the code repository. This is a demo repo that is mostly empty, but in reality this would be our whole codebase.

   > https://github.com/malerba423/transition-git-demo/

   > click the green **Code** button

   > click the **Open with Github Desktop** button

   > it will download the code and by default it will be saved to this directory `C:/Users/...../Documents/Github/transition-git-demo` directory

3. Install git and git-ftp. You can use all the defaults when installing git and git-ftp. Git is a source control management system. Git is what lets us version our files easily. Git-ftp is a tool that allows us to FTP only files that have changed since the last FTP, rather than blindly uploading everything again.

   > see instructions here:<br/> https://github.com/git-ftp/git-ftp/blob/master/INSTALL.md

4. Add git ftp environment configurations

   > open **git bash**

   > in the git bash console, navigate to the directory from step two: e.g. ...

   ```
   cd ~/Documents/Github/transition-git-demo
   ```

   > run the following commands:

   ```
   git config git-ftp.dev.user your-ftp-user-here
   git config git-ftp.dev.password your-ftp-password-here
   git config git-ftp.dev.url ftp.transitionbikesdev.com/JoelTest
   ```

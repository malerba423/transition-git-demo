# steps to get set up for doing development

1. Install github desktop. You can use all the defaults when installing Github Desktop. Github desktop is just a GUI for git.

   > https://desktop.github.com/

2. Download the code repository. This is a demo repo that is mostly empty, but in reality this would be our whole codebase.

   > https://github.com/malerba423/transition-git-demo/

   > click the green **Code** button

   > click the **Open with Github Desktop** button

   > it will download the code and by default it will be saved to the `~/Documents/Github/transition-git-demo` directory

3. Install git and git-ftp. You can use all the defaults when installing git and git-ftp. Git is a source control management system. Git is what lets us version our files easily. We can version files, maintain visibility of old versions of files, and not have to do the underscore naming that we have been doing. Git-ftp is a tool that allows us to FTP only files that have changed since the last FTP, rather than blindly uploading everything again.

   > see install instructions here:<br/> https://github.com/git-ftp/git-ftp/blob/master/INSTALL.md

4. Add git ftp environment configurations

   > from your start menu, open **git bash**

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

5. These are some zsh functions that you may want to add. Possibly would need bash or powershell versions?

   > `push-dev` function that accepts a branch name and pushes that branch to dev env. if no branch is supplied it defaults to master

   ```
   function push-dev () {
     branch=$1
     if [ "$branch" = "" ]; then
       branch="master"
     fi

     echo "pushing $branch to dev environment..."
     git ftp push -s dev -b $branch;
   }
   ```

   > `push-prod` function that always pushes master to prod env

   ```
   function push-prod () {
     echo "pushing master to prod environment..."
     git ftp push -s prod -b master;
   }
   ```

   > `compare-dev` function that compares current contents of DEV server to master branch

   ```
   function compare-dev () {
     git ftp -s dev log | head -1 | grep -o -e " .*" | xargs -I {} sh -c "echo https://github.com/malerba423/transition-git-demo/compare/{}...HEAD;"
   }
   ```

   > `compare-prod` function that compares current contents of PROD server to master branch

   ```
   function compare-prod () {
     git ftp -s prod log | head -1 | grep -o -e " .*" | xargs -I {} sh -c "echo https://github.com/malerba423/transition-git-demo/compare/{}...HEAD;"
   }
   ```

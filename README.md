# steps to get set up for doing development

1. install github desktop. You can use all the defaults when installing Github Desktop.

   > https://desktop.github.com/

2. download the code repository

   > https://github.com/malerba423/transition-git-demo/

   > click the green **Code** button

   > click the **Open with Github Desktop** button

   > it will download the code and by default it will be saved to the `/Documents/Github/transition-git-demo` directory

3. install git and git-ftp. You can use all the defaults when installing git and git-ftp.

   > see instructions here:<br/> https://github.com/git-ftp/git-ftp/blob/master/INSTALL.md

4. add git ftp environment configurations

   > open **git bash**

   > in the git bash console, navigate to the directory from step two: e.g. ...<br/><br/> `cd ~/Documents/Github/transition-git-demo`

   > run the following commands: <br/><br/> `git config git-ftp.dev.user your-ftp-user-here` <br/> `git config git-ftp.dev.password your-ftp-password-here` <br/> `git config git-ftp.dev.url ftp.transitionbikesdev.com/JoelTest`

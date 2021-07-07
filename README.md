# transition-website-test

# steps to get set up for doing development

1. install git and git-ftp

   > see instructions here https://github.com/git-ftp/git-ftp/blob/master/INSTALL.md

2. add git ftp configurations

   > git-ftp add-scope dev
   > git config git-ftp.dev.user yourDevFtpUser
   > git config git-ftp.dev.password yourDevFtpPass
   > git config git-ftp.dev.url ftp.transitionbikesdev.com/JoelTest

   > git-ftp add-scope prod
   > git config git-ftp.prod.user yourProdFtpUser
   > git config git-ftp.prod.password yourProdFtpPass
   > git config git-ftp.prod.url ftp.transitionbikes.com/JoelTest

3. tell git-ftp that the ftp server is already up to date

   > git-ftp catchup

### Show / hide home , trash icon from desktop
  - Options - icon_names
     - : show-home
     - : show-trash

  - true : show , false : hide

  `$ gsettings set org.gnome.shell.extensions.desktop-icons <icon_name> <true/false>`
  
====================================================================================================

### If dock (panel) not updating (show /hide) app icon when it close or open  <!-- ([Original](https://askubuntu.com/questions/1254414/ubuntu-20-04-not-updating-icons-on-dock/1277165#1277165)) -->
  - edit below file

  `$ sudo nano /usr/share/gnome-shell/extensions/ubuntu-dock@ubuntu.com/dash.js`

  - Update as following :

  ```
  let firstIcon = firstButton.icon;

    // Enforce the current icon size during the size request
    firstIcon.setIconSize(this.iconSize);
  ```
   - With :

  ```
    let firstIcon = firstButton.icon;

    // Enforce the current icon size during the size request
    if(firstIcon){
      firstIcon.setIconSize(this.iconSize);
    }
  ```
  Then reload the gnome shell using `Alt+F2` then `r`, the issue was gone!
  
  ====================================================================================================


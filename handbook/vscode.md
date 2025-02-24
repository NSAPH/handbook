# VS Code

## Background and Installation
VS Code, or Visual Studio Code, is a popular tool that allows for users to work in a variety of languages, including Python, Python notebooks, R, C, and more, all from one app.
It also can work with Git and Docker. It is not currently an option as an interactive app in FASSE like RStudio or Jupyter, but you can still use VS Code in CANNON/FASSE fairly easily, in 2 ways: 

1. **Virtual Desktop**  
2. **SSH Tunnel**  

## Setting Up a Virtual Desktop  

1. Launch **Remote Desktop** in CANNON/FASSE and follow the steps to create a session.  
2. Open VS Code: In a new Terminal window, run:  
   ```bash
   module load vscode
   code .
   ```  
   If you want a specific version of VS Code, you can type 
   ```bash
   module avail vscode
   ```
    to show the available options, and then load your desired option.
3. Configure your `.bashrc` file to load necessary modules automatically:  
   ```bash
   # .bashrc

   # Source global definitions
   if [ -f /etc/bashrc ]; then
       . /etc/bashrc
   fi

   function mm() {
       module load vscode 
       module load git
       module load python
   } 

   export MY_NSAPH_SSH_USERNAME="USERNAME"
   export MY_NSAPH_SSH_PASSWORD="PASSWORD"
   export http_proxy=http://rcproxy.rc.fas.harvard.edu:3128
   export https_proxy=http://rcproxy.rc.fas.harvard.edu:3128
   WORK="/n/dominici_lab/lab"
   ```  
4. Load VS Code, Git, and Python by running your function in Terminal (e.g., `mm`).  

> **Tip:** For more details, watch this [tutorial video](https://harvard.zoom.us/rec/play/Mu7_kI9FOmEnKsZrhZ-9AB8opY0ou_biKTUon6xu7aSBdcyAd_atViYGXcCurJr9DeBvlZoWj-fBJWtH.OsgEPAqi2glckinb?continueMode=true).  

### Installing Extensions  
If you prefer not to configure `.bashrc`, you can install language support manually:  
1. Open **Extensions** from the sidebar.  
2. Install language support for Python, Jupyter, Java, and more.  
3. Customize VS Code with extensions for Git visualization, text editing, and themes.  

> **Note:** If you receive a message about an outdated Git version, run:  
> ```bash
> module load git/2.17.0-fasrc01
> ```  
> before launching VS Code.  

## Setting Up an SSH Tunnel  

These directions are adapted from the official [VS Code SSH setup guide](https://code.visualstudio.com/docs/remote/ssh).  

### Pre-requisites  
Before setting up the SSH Tunnel, ensure your `.bashrc` file is configured as shown above.  

### Installation on Your Machine  
1. Install an [OpenSSH-compatible SSH client](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-client) if needed.  
2. Install [Visual Studio Code](https://code.visualstudio.com/).  
3. Install the [Remote-SSH extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh).  
4. Set up an SSH host by following the instructions for:  
   - **[Linux](https://code.visualstudio.com/docs/remote/troubleshooting#_installing-a-supported-ssh-server)**  
   - **[Windows](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui&pivots=windows-server-2025)**  
   - **[macOS](https://support.apple.com/guide/mac-help/allow-a-remote-computer-to-access-your-mac-mchlp1066/mac)**  
   - Or create an **[Azure VM](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu)**  


### Connecting to CANNON/FASSE  
1. In VS Code, open the **Command Palette** (`F1` or `⇧⌘P`).  
2. Select **Remote-SSH: Connect to Host...** and enter:  
   - `username@login.rc.fas.harvard.edu` (for CANNON)  
   - `username@fasselogin.rc.fas.harvard.edu` (for FASSE)  
3. Enter your **Harvard password**, followed by your **multi-factor authentication code** (e.g., Microsoft Authenticator, Duo).  
4. VS Code will establish the connection, displaying progress notifications and logs in the **Remote - SSH output channel**.  
5. Once connected, you’ll see an empty VS Code window. The **Status Bar** (bottom left corner) shows the active remote session.  
6. Open a folder or workspace using **File > Open...**, or clone a Git repository, just as you would locally.  
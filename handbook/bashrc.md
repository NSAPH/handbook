# How to set up a .bashrc file

The `.bashrc` file is a script executed whenever a new terminal session starts in an interactive, non-login shell. It's used to configure the environment, define aliases, set environment variables, and customize the command prompt. This is important, especially when working on data analysis to ensure reproducibility. Even more so when working in CANNON and FASSE, as certain settings must be changed to allow you to use common tools like Python, Git, and VS Code. 

## Setting up a `.bashrc` file in CANNON/FASSE:
1. Log into CANNON/FASSE and open Terminal
2. Navigate to your home directory. There should already by a `.bashrc` file in this directory. 
3. Open and edit it with at least the following configurations to allow you to use Python, Git, and VS Code. 

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
   4. Load the the modules configured in the `.bashrc ` by running your function in Terminal (e.g., `mm`)
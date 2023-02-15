# VS Code

## Background and Installation
VS Code, or Visual Studio Code, is a popular tool that allows for users to work in a variety of languages, including Python, Python notebooks, R, C, and more, all from one app.
It also can work with Git and Docker. It is not currently an option as an interactive app in FASSE like RStudio or Jupyter, but you can still use VS Code in FASSE fairly easily.

To open up VS Code, first open up a remote desktop in FASSE. Open up a new terminal window. 

In the terminal, you can type `module load vscode` to load the default version of vscode, and then `code .` to open it up. 
If you want a specific version of VS Code, you can type `module avail vscode` to show the available options, and then load your desired option.

## Set Up and Extensions 
When you first use VS Code, you will have to install the languages you are interested in working with. 
To do that, first click the sidebar icon which says extensions. Then you can select from a variety of languages and other extensions. 
Some options are Python, Jupyter, Java, and more. There are also extensions for how you want your text editing to appear, Git visualizations, and more.

Note: if you get a message about VS Code working best with Git version >2 and are currently using an older version of Git, you can also run `module load git/2.17.0-fasrc01` before opening up your VS Code window.
